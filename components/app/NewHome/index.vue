<template>
  <div>
    <header class="header-global">
      <nav id="navbar-main" class="navbar navbar-main navbar-expand-lg navbar-transparent navbar-light">
        <div class="container">
          <a class="navbar-brand mr-lg-4" href="https://www.serverless-devs.com/index.html">
            <img src="https://www.serverless-devs.com/logo.png" style="width: 89px; height: 49px">
          </a>
          <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbar_global"
            aria-controls="navbar_global" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="navbar-collapse collapse" id="navbar_global">
            <div class="navbar-collapse-header">
              <div class="row">
                <div class="col-6 collapse-brand">
                  <a href="https://www.serverless-devs.com/index.html">
                    <h3 style="color: white">Serverless Devs</h3>
                  </a>
                </div>
                <div class="col-6 collapse-close">
                  <button type="button" class="navbar-toggler" data-toggle="collapse" data-target="#navbar_global"
                    aria-controls="navbar_global" aria-expanded="false" aria-label="Toggle navigation">
                    <span></span>
                    <span></span>
                  </button>
                </div>
              </div>
            </div>
            <ul class="navbar-nav navbar-nav-hover align-items-lg-center" style="margin-top: 12px">
              <li class="nav-item dropdown">
                <a href="#" class="nav-link" data-toggle="dropdown" role="button">
                  <i class="ni ni-ui-04 d-lg-none"></i>
                  <span class="nav-link-inner--text"><b>开始与文档</b></span>
                </a>
                <div class="dropdown-menu dropdown-menu-xl">
                  <div class="dropdown-menu-inner">
                    <a href="https://docs.serverless-devs.com/serverless-devs/quick_start"
                      class="media d-flex align-items-center">
                      <div class="icon icon-shape bg-gradient-primary rounded-circle text-white">
                        <i class="ni ni-spaceship"></i>
                      </div>
                      <div class="media-body ml-3">
                        <h6 class="heading text-primary mb-md-1">快速开始</h6>
                        <p class="description d-none d-md-inline-block mb-0"><b>快速开始使用 Serverless
                            Devs</b></p>
                      </div>
                    </a>
                    <a href="http://docs.serverless-devs.com" class="media d-flex align-items-center">
                      <div class="icon icon-shape bg-gradient-warning rounded-circle text-white">
                        <i class="ni ni-ui-04"></i>
                      </div>
                      <div class="media-body ml-3">
                        <h5 class="heading text-warning mb-md-1">文档相关</h5>
                        <p class="description d-none d-md-inline-block mb-0"><b>查看 Serverless Devs 与相关
                            Package 文档</b></p>
                      </div>
                    </a>
                  </div>
                </div>
              </li>
              <li class="nav-item dropdown">
                <a href="http://www.devsapp.cn/" class="nav-link" data-toggle="dropdown" role="button">
                  <i class="ni ni-collection d-lg-none"></i>
                  <span class="nav-link-inner--text"><b>Registry</b></span>
                </a>
                <div class="dropdown-menu">
                  <a href="http://www.devsapp.cn/application.html" class="dropdown-item">应用</a>
                  <a href="http://www.devsapp.cn/component.html" class="dropdown-item">组件</a>
                  <a href="http://www.devsapp.cn/plugin.html" class="dropdown-item">插件</a>
                  <a href="http://www.devsapp.cn/faq.html" class="dropdown-item">常见问答</a>
                </div>
              </li>
              <!-- <li class="nav-item dropdown">
                <a href="http://i.serverless-devs.com/article" class="nav-link" data-toggle="dropdown" role="button">
                  <i class="ni ni-collection d-lg-none"></i>
                  <span class="nav-link-inner--text"><b>Serverless 社区</b></span>
                </a>
                <div class="dropdown-menu">

                  <a href="http://i.serverless-devs.com/" class="dropdown-item">社区首页</a>
                  <a href="http://i.serverless-devs.com/portal.php?mod=list&catid=20" class="dropdown-item">社区专栏</a>
                </div>
              </li> -->
              <li class="nav-item dropdown">
                <a href="http://i.serverless-devs.com/portal.php?mod=list&catid=6" class="nav-link" role="button">
                  <i class="ni ni-collection d-lg-none"></i>
                  <span class="nav-link-inner--text"><b>社区工作组</b></span>
                </a>
              </li>
              <li class="nav-item dropdown">
                <a href="/en/index.html" class="nav-link" role="button">
                  <i class="ni ni-collection d-lg-none"></i>
                  <span class="nav-link-inner--text"><b>English</b></span>
                </a>
              </li>
            </ul>
            <ul class="navbar-nav align-items-lg-center ml-lg-auto" style="margin-top: 12px">
              <span class="text-white alpha-7 ml-3">Star on</span>
              <a href="https://github.com/serverless-devs/serverless-devs" target="_blank" title="Support us on Github">
                <img src="https://www.serverless-devs.com/assets/img/brand/github-white-slim.png"
                  style="height: 22px; margin-top: -3px">
              </a>
            </ul>
          </div>
        </div>
      </nav>
    </header>
    <main>
      <div class="position-relative">
        <!-- shape Hero -->
        <section class="section-shaped my-0">
          <div class="shape shape-style-1 shape-skew shape-primary">
            <span></span>
            <span></span>
            <span></span>
            <span></span>
            <span></span>
            <span></span>
            <span></span>
            <span></span>
            <span></span>
          </div>
          <div class="container shape-container d-flex">
            <div class="col px-0">
              <div class="row">
                <div class="col-lg-6">
                  <h1 class="display-3  text-white"><b>文档中心</b>
                    <span>
                      <font size="5"><b>Serverless Devs 已支持多云厂商与开源项目</b></font>
                    </span>
                  </h1>
                  <p class="lead  text-white"><b>基于 SDM 模型，Serverless Devs 已经实现了对阿里云、百度云、华为云等多家云厂商的 FaaS
                      平台的支持，与此同时也实现了与 OpenFunction 等开源项目的进一步集成。</b></p>
                  <div class="btn-wrapper">
                    <a href="https://github.com/serverless-devs/serverless-devs"
                      class="btn btn-white btn-icon mb-3 mb-sm-0">
                      <span class="btn-inner--icon"><i class="fa fa-code"></i></span>
                      <span class="btn-inner--text">开源项目</span>
                    </a>
                    <a href="https://docs.serverless-devs.com/serverless-devs/quick_start"
                      class="btn btn-primary btn-icon mb-3 mb-sm-0" ni-spaceship>
                      <span class="btn-inner--icon"><i class="ni ni-spaceship"></i></span>
                      <span class="btn-inner--text">快速开始</span>
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>
        <!-- 1st Hero Variation -->
      </div>
      <section class="section section-lg pt-lg-0 mt--200">
        <div class="container">
          <div class="row justify-content-center">
            <div class="col-lg-12">
              <div class="row row-grid">
                <div class="col-lg-4">
                  <div class="card card-lift--hover shadow border-0">
                    <a href="/serverless-devs/readme" class="card-body py-5">
                      <h3 class="text" style="color: black"><b>Serverless Devs</b>
                      </h3>
                      <p class="description mt-3"><b>🔥🔥🔥 Serverless Devs 开发者工具文档</b>
                      </p>
                    </a>
                  </div>
                </div>
                <div class="col-lg-4">
                  <div class="card card-lift--hover shadow border-0">
                    <a href="/sdm/readme" class="card-body py-5">
                      <h3 class="text" style="color: black"><b>SDM 模型</b>
                      </h3>
                      <p class="description mt-3"><b>Serverless Devs Model 模型文档</b></p>
                    </a>
                  </div>
                </div>
                <div class="col-lg-4">
                  <div class="card card-lift--hover shadow border-0">
                    <a href="/serverless-registry/readme" class="card-body py-5">
                      <h3 class="text" style="color: black"><b>Serverless Registry</b>
                      </h3>
                      <p class="description mt-3"><b>🔥 Serverless Registry 工具文档</b></p>
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="container" style="margin-top: 50px">
          <div class="row justify-content-center">
            <div class="col-lg-12">
              <div class="row row-grid">
                <div class="col-lg-4">
                  <div class="card card-lift--hover shadow border-0">
                    <a href="/fc/readme" class="card-body py-5">
                      <h3 class="text" style="color: black"><b>函数计算（FC）</b>
                      </h3>
                      <p class="description mt-3"><b>🔥🔥🔥 阿里云函数计算（FC）组件文档</b>
                      </p>
                      <div>
                        <span class="badge badge-pill badge-primary">云服务</span>
                        <span class="badge badge-pill badge-primary">函数计算</span>
                      </div>
                    </a>
                  </div>
                </div>
                <div class="col-lg-4">
                  <div class="card card-lift--hover shadow border-0">
                    <a href="/lambda/readme" class="card-body py-5">
                      <h3 class="text" style="color: black"><b>Lambda</b>
                      </h3>
                      <p class="description mt-3"><b>🔥🔥🔥 AWS Lambda 组件文档</b></p>
                      <div>
                        <span class="badge badge-pill badge-primary">云服务</span>
                        <span class="badge badge-pill badge-primary">函数计算</span>
                      </div>
                    </a>
                  </div>
                </div>
                <div class="col-lg-4">
                  <div class="card card-lift--hover shadow border-0">
                    <a href="/cfc/readme" class="card-body py-5">
                      <h3 class="text" style="color: black"><b>函数计算（CFC）</b>
                      </h3>
                      <p class="description mt-3"><b>🔥 百度智能云函数计算（CFC）组件文档</b></p>
                      <div>
                        <span class="badge badge-pill badge-primary">云服务</span>
                        <span class="badge badge-pill badge-primary">函数计算</span>
                      </div>
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="container" style="margin-top: 50px">
          <div class="row justify-content-center">
            <div class="col-lg-12">
              <div class="row row-grid">
                <div class="col-lg-4">
                  <div class="card card-lift--hover shadow border-0">
                    <a href="/fg/readme" class="card-body py-5">
                      <h3 class="text" style="color: black"><b>函数计算工作流（FG）</b>
                      </h3>
                      <p class="description mt-3"><b>🔥🔥 华为云函数计算工作流（FG）组件文档</b>
                      </p>
                      <div>
                        <span class="badge badge-pill badge-primary">云服务</span>
                        <span class="badge badge-pill badge-primary">函数计算</span>
                      </div>
                    </a>
                  </div>
                </div>
                <div class="col-lg-4">
                  <div class="card card-lift--hover shadow border-0">
                    <a href="/scf/readme" class="card-body py-5">
                      <h3 class="text" style="color: black"><b>云函数（SCF）</b>
                      </h3>
                      <p class="description mt-3"><b>腾讯云云函数（SCF）组件文档</b></p>
                      <div>
                        <span class="badge badge-pill badge-primary">云服务</span>
                        <span class="badge badge-pill badge-primary">函数计算</span>
                      </div>
                    </a>
                  </div>
                </div>
                <div class="col-lg-4">
                  <div class="card card-lift--hover shadow border-0">
                    <a href="/open-function/readme" class="card-body py-5">
                      <h3 class="text" style="color: black">
                        <b>OpenFunction</b>
                      </h3>
                      <p class="description mt-3"><b>开源框架 OpenFunction 组件文档</b></p>
                      <div>
                        <span class="badge badge-pill badge-primary">开源项目</span>
                        <span class="badge badge-pill badge-primary">函数计算</span>
                      </div>
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="container" style="margin-top: 50px">
          <div class="row justify-content-center">
            <div class="col-lg-12">
              <div class="row row-grid">
                <div class="col-lg-4">
                  <div class="card card-lift--hover shadow border-0">
                    <a href="/fnf/readme" class="card-body py-5">
                      <h3 class="text" style="color: black"><b>Serverless 工作流</b>
                      </h3>
                      <p class="description mt-3"><b>阿里云 Serverless 工作流（FNF）组件文档</b>
                      </p>
                      <div>
                        <span class="badge badge-pill badge-primary">云服务</span>
                        <span class="badge badge-pill badge-primary">Workflow</span>
                      </div>
                    </a>
                  </div>
                </div>
                <div class="col-lg-4">
                  <div class="card card-lift--hover shadow border-0">
                    <a href="/sae/readme" class="card-body py-5">
                      <h3 class="text" style="color: black"><b>Serverless 应用引擎</b>
                      </h3>
                      <p class="description mt-3"><b>阿里云 Serverless 应用引擎（SAE）组件文档</b></p>
                      <div>
                        <span class="badge badge-pill badge-primary">云服务</span>
                        <span class="badge badge-pill badge-primary">应用托管</span>
                      </div>
                    </a>
                  </div>
                </div>
                <div class="col-lg-4">
                  <div class="card card-lift--hover shadow border-0">
                    <div class="card-body py-5">
                      <h3 class="text" style="color: black">
                        <b>Laf（即将支持）</b>
                      </h3>
                      <p class="description mt-3"><b>开源项目 Laf 组件文档</b></p>
                      <div>
                        <span class="badge badge-pill badge-primary">开源项目</span>
                        <span class="badge badge-pill badge-primary">云开发</span>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>
    <footer class="footer has-cards">
      <div class="container">
        <div class="row row-grid align-items-center my-md">
          <div class="col-lg-6">
            <h3 class="text-primary font-weight-light mb-2">感谢您对我们的关注</h3>
            <h4 class="mb-0 font-weight-light">让我们一起玩转 Serverless 架构</h4>
          </div>
          <div class="col-lg-6 text-lg-center btn-wrapper">
            <a target="_blank" href="https://github.com/serverless-devs/serverless-devs"
              class="btn btn-neutral btn-icon-only btn-wechat btn-round btn-lg" data-toggle="tooltip"
              data-original-title="Star on Github">
              <i class="fa fa-github"></i>
            </a>
            <a target="_blank" href="https://gitee.com/serverless-devs/serverless-devs"
              class="btn btn-neutral btn-icon-only btn-git btn-round btn-lg" data-toggle="tooltip"
              data-original-title="Star on Gitee">
              <i class="fa fa-git"></i>
            </a>
            <a target="_blank" href="http://docs.serverless-devs.com"
              class="btn btn-neutral btn-icon-only btn-git btn-round btn-lg" data-toggle="tooltip"
              data-original-title="Docs">
              <i class="fa fa-book"></i>
            </a>
            <a target="_blank" href="http://www.devsapp.cn"
              class="btn btn-neutral btn-icon-only btn-git btn-round btn-lg" data-toggle="tooltip"
              data-original-title="Serverless Registry">
              <i class="fa fa-desktop"></i>
            </a>
            <a target="_blank" href="http://i.serverless-devs.com"
              class="btn btn-neutral btn-icon-only btn-git btn-round btn-lg" data-toggle="tooltip"
              data-original-title="iServerless">
              <i class="fa fa-user"></i>
            </a>
          </div>
        </div>
        <hr>
        <div class="row align-items-center justify-content-md-between">
          <div class="col-md-6">
            <div class="copyright">
              &copy; 2022
              <a href="https://www.serverless-devs.com" target="_blank">Serverless Devs</a>.
            </div>
          </div>
          <div class="col-md-6">
            <ul class="nav nav-footer justify-content-end">
              <li class="nav-item">
                <a class="nav-link nav-link-icon" href="https://github.com/serverless-devs/serverless-devs"
                  target="_blank" data-toggle="tooltip" title="Github Repo">
                  <i class="fa fa-github-alt"></i>
                  <span class="nav-link-inner--text d-lg-none">Github</span>
                </a>
              </li>
              <li class="nav-item">
                <a class="nav-link nav-link-icon" href="https://gitee.com/serverless-devs/Serverless-Devs"
                  target="_blank" data-toggle="tooltip" title="Gitee Repo">
                  <i class="fa fa-git"></i>
                  <span class="nav-link-inner--text d-lg-none">Gitee</span>
                </a>
              </li>
              <li class="nav-item">
                <a href="http://docs.serverless-devs.com" class="nav-link" target="_blank">帮助文档</a>
              </li>
              <li class="nav-item">
                <a href="http://i.serverless-devs.com" class="nav-link" target="_blank">Serverless 社区</a>
              </li>
              <li class="nav-item">
                <a href="http://www.devsapp.cn" class="nav-link" target="_blank">Registry</a>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  head() {
    return {
      title: '文档 - Serverless Devs - Serverless 应用全生命周期管理工具 / Serverless 中文社区',
      meta: [
        { name: "viewport", content: "width=device-width, initial-scale=1, shrink-to-fit=no" },
        {
          name: "description",
          content: "Serverless Devs 是一个开源开放的 Serverless 开发者平台，致力于为开发者提供强大的工具链体系。通过该平台，开发者不仅可以一键体验多云 Serverless 产品，极速部署 Serverless 项目，还可以在 Serverless 应用全生命周期进行项目的管理，并且非常简单快速的将 Serverless Devs 与其他工具/平台进行结合，进一步提升研发、运维效能。"
        },
        { name: "author", content: "Serverless Devs" },
        { name: "keywords", content: "Serverless, Serverless Devs, 中文社区, Serverless 社区" },
      ],
      link: [
        { rel: 'icon', href: "https://www.serverless-devs.com/assets/img/brand/favicon.png", type: "image/png" },
        { href: "https://fonts.googleapis.com/css?family:Open+Sans:300,400,600,700", rel: "stylesheet" },
        { href: "https://www.serverless-devs.com/assets/vendor/nucleo/css/nucleo.css", rel: "stylesheet" },
        { href: "https://www.serverless-devs.com/assets/vendor/font-awesome/css/font-awesome.min.css", rel: "stylesheet" },
        { type: "text/css", href: "https://www.serverless-devs.com/assets/css/argon.css?v:1.0.0", rel: "stylesheet" }
      ],
      script: [
        { src: "https://www.serverless-devs.com/assets/vendor/jquery/jquery.min.js" },
        { src: "https://www.serverless-devs.com/assets/vendor/popper/popper.min.js" },
        { src: "https://www.serverless-devs.com/assets/vendor/bootstrap/bootstrap.min.js" },
        { src: "https://www.serverless-devs.com/assets/vendor/headroom/headroom.min.js" },
        { src: "https://www.serverless-devs.com/assets/js/argon.js?v=1.0.0" },
      ]
    }
  },
  computed: {
    ...mapGetters(["settings"]),
  },
};
</script>
