# 简单实现锚点的双向定位

### html代码
```html
<!DOCTYPE html>
<html lang="zh-CN">
  <head>
    <meta charset="utf-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width,initial-scale=1.0" />
    <link rel="shortcut icon" href="favicon.ico">
    <link rel="stylesheet" href="//at.alicdn.com/t/font_1313960_ayr6ey07oki.css" />
    <link rel="stylesheet" href="/assets/css/reset.css" />
    <link rel="stylesheet" href="/assets/css/main.css" />
    <link rel="stylesheet" href="/assets/css/template.css" />
    <script src="/libs/zepto/1.2.0/zepto.min.js"></script>
    <script src="/assets/js/template.js"></script>
    <title>产品文档 - 模板</title>
  </head>

  <body>
    <!-- 顶部栏 -->
    <header class="pt-template-header" id="header"></header>
    <section class="pt-template-content">
      <!-- 左侧导航栏 -->
      <nav class="pull-left clearfix pt-template-content-nav">
        <div class="nav-header">
          <p>全部文档</p>
          <p><i class="iconfont icon-menu" id="allProduct"></i></p>
        </div>
        <div class="nav-menu">
          <div class="nav-menu-title" id="mavMenuTitle">账号管理</div>
          <div class="menu-wrap">
            <div class="menu-list">
              <ul role="tree" id="menuTree" class="menu-item">
                <li role="treeitem" aria-expanded="false" aria-haspopup="true" aria-level="1">
                  <a href="javascript:;" class="item" title="产品介绍" data-id="1">
                    产品介绍<i class="iconfont icon-jiantouxiao"></i>
                  </a>
                  <ul role="group">
                    <li role="treeitem" aria-expanded="false" aria-haspopup="false" aria-level="2">
                      <a href="2.html" class="item" title="什么是云容器引擎" data-id="2">什么是云容器引擎</a>
                    </li>
                    <li role="treeitem" aria-expanded="false" aria-haspopup="false" aria-level="2">
                      <a href="3.html" class="item" title="容器全栈产品" data-id="3">容器全栈产品</a>
                    </li>
                    <li role="treeitem" aria-expanded="false" aria-haspopup="false" aria-level="2">
                      <a href="4.html" class="item" title="产品优势" data-id="4">产品优势</a>
                    </li>
                    <li role="treeitem" aria-expanded="false" aria-haspopup="true" aria-level="2">
                      <a href="javascript:;" class="item" title="与其它云服务关系" data-id="5">
                        与其它云服务关系<i class="iconfont icon-jiantouxiao"></i>
                      </a>
                      <ul role="group">
                        <li role="treeitem" aria-expanded="false" aria-haspopup="false" aria-level="3">
                          <a href="6.html" class="item" title="百度云" data-id="6">百度云</a>
                        </li>
                        <li role="treeitem" aria-expanded="false" aria-haspopup="false" aria-level="3">
                          <a href="7.html" class="item" title="腾讯云" data-id="7">腾讯云</a>
                        </li>
                        <li role="treeitem" aria-expanded="false" aria-haspopup="false" aria-level="3">
                          <a href="8.html" class="item" title="华为云" data-id="8">华为云</a>
                        </li>
                        <li role="treeitem" aria-expanded="false" aria-haspopup="false" aria-level="3">
                          <a href="9.html" class="item" title="阿里云" data-id="9">阿里云</a>
                        </li>
                      </ul>
                    </li>
                  </ul>
                </li>
                <li role="treeitem" aria-expanded="false" aria-haspopup="false" aria-level="1">
                  <a href="10.html" class="item" title="特性指南" data-id="10">特性指南</a>
                </li>
                <li role="treeitem" aria-expanded="false" aria-haspopup="false" aria-level="1">
                  <a href="11.html" class="item" title="控制台指南" data-id="11">控制台指南</a>
                </li>
                <li role="treeitem" aria-expanded="false" aria-haspopup="false" aria-level="1">
                  <a href="12.html" class="item" title="工具指南" data-id="12">工具指南</a>
                </li>
                <li role="treeitem" aria-expanded="false" aria-haspopup="false" aria-level="1">
                  <a href="13.html" class="item" title="快速入门" data-id="13">快速入门</a>
                </li>
                <li role="treeitem" aria-expanded="false" aria-haspopup="false" aria-level="1">
                  <a href="14.html" class="item" title="价格说明" data-id="14">价格说明</a>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </nav>
      <!-- 文章内容 -->
      <main class="pull-left clearfix pt-template-content-main">
        <header class="main-search">
          <div class="search-input">
            <input type="text" placeholder="搜索本产品文档" class="search-input_inner" id="searchInput" />
            <span class="input-suffix">
              <i class="iconfont icon-guanbi-bad" id="clearIcon"></i>
            </span>
          </div>
          <button class="search-btn"><i class="iconfont icon-search"></i></button>
        </header>
        <section class="main-container" id="main">
          <h4 class="achor-top" id="15">初始化数据盘场景及磁盘分区形式介绍</h4>
          <p>云容器引擎（Cloud Container Engine，简称CCE）提供高度可扩展的、高性能的企业级Kubernetes集群，支持运行Docker容器。借助云容器引擎，您可以在华为云上轻松部署、管理和扩展容器化应用程序。</p>
          <p>云容器引擎深度整合华为云高性能的计算（ECS/BMS）、存储（EVS/OBS/SFS）等服务，并支持GPU、ARM、FPGA等异构计算架构，支持多可用区（Available zone，简称AZ）、多区域（Region）容灾等技术构建高可用Kubernetes集群。</p>
          <p>华为云是全球首批Kubernetes认证服务提供商（Kubernetes Certified Service Provider，KCSP），是国内最早投入Kubernetes社区的厂商，是容器开源社区主要贡献者和容器生态领导者。华为云也是CNCF云原生计算基金会的创始成员及白金会员，云容器引擎是全球首批通过CNCF基金会Kubernetes一致性认证的容器服务。</p>
          <p>您可以通过控制台、Kubectl命令行、Kubernetes API使用云容器引擎服务。</p>
          <h4 class="achor-top" id="16">产品功能</h4>
          <p>云容器引擎提供了Kubernetes集群管理、容器应用全生命周期管理、应用服务网格、Helm应用模板、插件管理、应用调度、监控与运维等容器全栈能力，为您提供一站式容器平台服务。</p>
          <h5>一站式部署和运维</h5>
          <p>使用云容器引擎，您可以一键创建Kubernetes容器集群，无需自行搭建Docker和Kubernetes集群。您可以通过云容器引擎自动化部署和一站式运维容器应用，使得应用的整个生命周期都在云容器引擎内高效完成。</p>
          <h5>支持多类型容器集群</h5>
          <p>通过云容器引擎您可以直接使用华为云高性能的弹性云服务器、裸金属服务器、GPU加速云服务器等多种异构基础设施，您可以根据业务需要在云容器引擎中快速创建混合集群、鲲鹏集群、裸金属集群和GPU容器集群，并通过云容器引擎对创建的集群进行统一管理。</p>
          <h4 class="achor-top" id="17">云容器引擎的优势</h4>
          <p>云容器引擎是基于业界主流的Docker和Kubernetes开源技术构建的容器服务，提供众多契合企业大规模容器集群场景的功能，在系统可靠性、高性能、开源社区兼容性等多个方面具有独特的优势，满足企业在构建容器云方面的各种需求。</p>
          <h5>简单易用</h5>
          <ul>
            <li>
              通过WEB界面一键创建Kubernetes集群，支持管理虚拟机节点或裸金属节点，支持虚拟机与物理机混用场景。
            </li>
            <li>
              一站式自动化部署和运维容器应用，整个生命周期都在容器服务内一站式完成。
            </li>
            <li>
              通过Web界面轻松实现集群节点和工作负载的扩容和缩容，自由组合策略以应对多变的突发浪涌。
            </li>
            <li>
              通过Web界面一键完成Kubernetes集群的升级。
            </li>
            <li>
              深度集成应用服务网格和Helm标准模板，真正实现开箱即用。
            </li>
          </ul>
          <h5>高性能</h5>
          <ol>
            <li>
              1、云容器引擎在 Docker 技术的基础上，为容器化的应用提供部署运行、资源调度、服务发现和动态伸缩等一系列完整功能，提高了大规模容器集群管理的便捷性。
            </li>
            <li>
              2、云容器引擎基于业界主流的Kubernetes 实现，完全兼容Kubernetes/Docker社区原生版本，与社区最新版本保持紧密同步，完全兼容Kubernetes API和Kubectl。
            </li>
            <li>
              3、云容器引擎在 Docker 技术的基础上，为容器化的应用提供部署运行、资源调度、服务发现和动态伸缩等一系列完整功能，提高了大规模容器集群管理的便捷性。
            </li>
            <li>
              4、云容器引擎基于业界主流的Kubernetes 实现，完全兼容Kubernetes/Docker社区原生版本，与社区最新版本保持紧密同步，完全兼容Kubernetes API和Kubectl。但有如下限制：
              <ul>
                <li>
                  如果创建的集群是“按需计费”，那么在该集群下创建的节点只能为“按需计费”。
                </li>
                <li>
                  如果创建的集群是“包年包月”，那么该集群下的节点可以为“按需计费”或者“包年包月”。
                </li>
                <li>
                  纳管的节点在“包年包月”场景下，无法通过集群为其续费，需用户单独续费。
                </li>
              </ul>
            </li>
          </ol>
          <h4 class="achor-top" id="18">使用云容器引擎</h4>
          <h4 class="achor-top" id="19">示例代码(默认样式)</h4>
          <code>
            function upgrade_ovs () {
              wget http://obs.cn-east-2.myhwclouds.com/cce-east/cce-openvswitch/openvswitch-1.0.RC10.SPC100.B050.tar.g
              mv /var/paas/kubernetes/canal/openvswitch /var/paas/kubernetes/canal/openvswitch.bak
              tar zxvf openvswitch-1.0.RC10.SPC100.B050.tar.gz -C /var/paas/kubernetes/canal/
              bash /var/paas/kubernetes/canal/openvswitch/can_ovs.sh install
              systemctl restart  ovsdb-server ovs-vswitchd 
            }
            upgrade_ovs
          </code>
          <h2></h2>
        </section>
      </main>
      <!-- 右侧锚点 -->
      <aside class="pull-left clearfix pt-template-content-anchor">
        <h5 class="anchor-title">本文导航</h5>
        <ul id="anchorList">
          <li>
            <a href="#15" title="初始化数据盘场景及磁盘分区形式介绍">
              <span>初始化数据盘场景及磁盘分区形式介绍</span>
            </a>
          </li>
          <li>
            <a href="#16" title="产品功能">
              <span>产品功能</span>
            </a>
          </li>
          <li>
            <a href="#17" title="云容器引擎的优势">
              <span>云容器引擎的优势</span>
            </a>
          </li>
          <li>
            <a href="#18" title="使用云容器引擎">
              <span>使用云容器引擎</span>
            </a>
          </li>
          <li>
            <a href="#19" title="示例代码(默认样式)">
              <span>示例代码(默认样式)</span>
            </a>
          </li>
      </ul>
      </aside>
    </section>

    <!-- nav down -->
    <div class="slide-nav-down" id="slideNavDown">
      <h2>全部产品</h2>
      <div class="app-list" id="appContainer">
          <span class="iconfont icon-tenantcenter" app-id="1">
            <label>账号管理</label>
          </span>
          <span class="iconfont icon-shouquan" app-id="2">
            <label>授权中心</label>
          </span>
          <span class="iconfont icon-sdjm" app-id="3">
            <label>三维建模</label>
          </span>
      </div>
    </div>
  </body>
</html>

```

### JavaScript代码
```javascript
// 监听内容区域滚动条, 设置锚点激活
function listenScroll ($) {
  // 页面加载默认调用(只执行一次)
  var onceId = $(document.querySelectorAll('.achor-top')[0]).attr('id');
  $('#anchorList li').removeClass('active');
  $('#anchorList li a[href="#'+ onceId +'"]').parent().addClass('active');
  // 滚动监听
  $('#main').on('scroll', function (e) {
    var mainElement = document.getElementById('main');
    // 可滚动容器距离浏览器顶部的距离
    var top = mainElement.offsetTop + 30;
    // 滚动条滚动的距离
    var scrollTop = mainElement.scrollTop;
    var list = document.querySelectorAll('.achor-top');
    // 符合条件的锚点ID
    var idList = [];
    // 当前需要激活的锚点ID
    var currentAchorId = '';
    for (var i = 0; i < list.length; i++) {
      if (scrollTop >= list[i].offsetTop - top) {
        idList.push('#' + $(list[i]).attr('id'));
      }
    }
    if (idList.length === 0) {
      currentAchorId = '#' + $(list[0]).attr('id');
    } else {
      currentAchorId = idList.pop();
    }
    $('#anchorList li').removeClass('active');
    $('#anchorList li a[href="'+ currentAchorId +'"]').parent().addClass('active');
  })
}

Zepto(function ($) {
  // 监听内容区域滚动条, 设置锚点激活
  listenScroll($);
});
```

### 实现效果

![效果图](./effect.gif)