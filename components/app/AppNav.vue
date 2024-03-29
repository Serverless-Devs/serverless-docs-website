<template>
  <aside
    class="w-full lg:w-1/5 lg:block fixed lg:relative inset-0 mt-16 lg:mt-0 z-30 bg-white dark:bg-gray-900 lg:bg-transparent lg:dark:bg-transparent"
    :class="{ block: menu, hidden: !menu }"
  >
    <div
      class="lg:sticky lg:top-16 overflow-y-auto h-full lg:h-auto lg:max-h-(screen-16)"
    >
      <ul class="p-4 lg:py-8 lg:pl-0 lg:pr-8">
        <li v-if="!settings.algolia" class="mb-4 lg:hidden">
          <AppSearch />
        </li>
        <li
          v-for="(docs, category, index) in categories"
          :key="category"
          class="mb-4"
          :class="{
            active: isCategoryActive(docs),
            'lg:mb-0': index === Object.keys(categories).length - 1,
          }"
        >
          <p
            v-if="category"
            class="mb-2 text-gray-500 uppercase tracking-wider font-bold text-sm lg:text-xs"
          >
            {{ category }}
          </p>
          <ul>
            <li
              v-for="doc of docs"
              :key="doc.slug"
              class="text-gray-700 dark:text-gray-300"
            >
              <NuxtLink
                :to="localePath(doc.to)"
                class="px-2 rounded font-medium py-1 hover:text-primary-500 flex items-center justify-between"
                active-class="text-primary-500 bg-primary-100 hover:text-primary-500 dark:bg-primary-900"
              >
                {{ doc.menuTitle || doc.title }}
                <client-only>
                  <span
                    v-if="isDocumentNew(doc)"
                    class="animate-pulse rounded-full bg-primary-500 opacity-75 h-2 w-2"
                  />
                </client-only>
              </NuxtLink>
            </li>
          </ul>
        </li>
      </ul>
    </div>
  </aside>
</template>

<script>
import { mapGetters } from "vuex";
import _ from "lodash";

export default {
  data() {
    return {
      categories: {},
    };
  },
  computed: {
    ...mapGetters(["settings", "githubUrls"]),
    menu: {
      get() {
        return this.$store.state.menu.open;
      },
      set(val) {
        this.$store.commit("menu/toggle", val);
      },
    },
    categoriesAll(){
      return this.$store.state.categories
    }
  },
  methods: {
    getDocPath(doc) {
      const basePath = this.$i18n.locale === "zh" ? "" : "/en";
      return `${basePath}/${doc.to}`;
    },
    getCategories() {
      const basePath = this.$i18n.locale === "zh" ? "" : "/en";
      const currentPath = this.$router.history.current.path;
      const docsSetting = _.find(this.settings.nav, item => item.name ==='docs');
      for(let doc of docsSetting.items) {
        const slugPath = `${basePath}/${doc.slug}/`;
        if (currentPath.startsWith(slugPath)) {
          return this.listCategories(`/${doc.slug}/`);
        }
      }
    },
    listCategories(path) {
      const cates = this.categoriesAll[this.$i18n.locale];
      const currentCates = {};
      _.each(cates, (item, key) => {
        if (!key) return;
        const cateItems = _.filter(item, (cate) =>
          cate.to.startsWith(path)
        );
        if (!_.isEmpty(cateItems)) {
          currentCates[key] = cateItems;
        }
      });
      return currentCates;
    },
    isCategoryActive(documents) {
      return documents.some((document) => this.getDocPath(document.to) === this.$route.fullPath);
    },
    isDocumentNew(document) {
      if (process.server) {
        return;
      }
      if (!document.version || document.version <= 0) {
        return;
      }

      const version = localStorage.getItem(`document-${document.slug}-version`);
      if (document.version > Number(version)) {
        return true;
      }

      return false;
    },
  },
  watch: {
    $route: {
      handler(to, from) {
        this.categories = this.getCategories();
      },
      immediate: true,
    },
    categoriesAll: {
      handler() {
        this.categories = this.getCategories();
      },
      deep: true,
      immediate: true,
    },
  },
};
</script>
