<template>
  <div>
    <span v-for="(link, index) in links" :key="link.name">
      <el-dropdown class="ml-4" v-if="link.items">
        <span
          :class="{
            'text-current': link.active,
            'text-gray-700': !link.active,
          }"
          class="text-base dark:text-gray-300 hover:text-primary-500 dark-hover:text-primary-500 cursor-pointer whitespace-no-wrap"
        >
          {{ $i18n.locale === "en" ? link.en_title : link.title }}
          <i class="el-icon-arrow-down el-icon--right"></i>
        </span>
        <el-dropdown-menu slot="dropdown">
          <el-dropdown-item
            v-for="(items, key) in link.items"
            :key="index + key"
            :divided="items.divided"
            :class="{
              'text-current': items.active,
              'text-gray-700': !items.active,
            }"
          >
            <NuxtLink :to="localePath(items.to)" class="inline-block h-full w-full">
              {{ $i18n.locale === "en" ? items.en_title : items.title }}
            </NuxtLink>
          </el-dropdown-item>
        </el-dropdown-menu>
      </el-dropdown>
      <NuxtLink
        v-else
        :to="localePath(link.to)"
        class="dark:text-gray-300 hover:text-primary-500 dark-hover:text-primary-500 ml-4 cursor-pointer whitespace-no-wrap"
        :class="{
          'text-current': link.active,
          'text-gray-700': !link.active,
        }"
      >
        {{ $i18n.locale === "en" ? link.en_title : link.title }}
      </NuxtLink>
    </span>
  </div>
</template>

<script>
import { useNav } from "~/plugins/nav";
import _ from "lodash";
import { mapGetters } from "vuex";
import { defineComponent } from "@nuxtjs/composition-api";

export default defineComponent({
  setup() {
    const { isHome, path, currentSlug } = useNav();
    return {
      isHome,
      path,
      currentSlug,
    };
  },
  computed: {
    ...mapGetters(["settings"]),
    links() {
      const currentSlug = this.currentSlug;
      const links = _.cloneDeep(this.settings.nav);
      _.each(links, (link) => {
        if (!link.items) {
          if (!currentSlug) {
            if (link.to === this.path) {
              link.active = true;
            }
          } else {
            link.active = link.slug === currentSlug;
          }
        } else {
          let hasActive;
          _.each(link.items, (item) => {
            item.active = item.slug === currentSlug;
            if (item.slug === currentSlug) {
              hasActive = true;
            }
          });
          if (hasActive) {
            link.active = true;
          }
          link.items = _.filter(link.items, (item) => (!item.isHide))
        }
      });
      return links;
    },
  },
});
</script>
