## 自定义的树组件DEMO

### 主页面容器
> owner 为主页面的vue实例

```html
<menu-tree-node
  v-for="child in menuList"
  :key="child.id"
  :level="1"
  :node="child"
  :owner="owner"
></menu-tree-node>
```

### 以下为组件内容
```html
<li role="menuitem"
  aria-expanded="false"
  :aria-haspopup="node.children.length > 0 ? 'true': 'false'"
  :aria-level="level">
  <a href="javascript:;" class="item" @click="nodeClick($event)">
    <div class="icon"><i class="iconfont icon-jiantouxiao"></i></div>
    <div class="text" :title="node.title">
      <span>{{ node.title }}</span>
    </div>
  </a>
  <ul role="group">
    <menu-tree-node-preview
      v-for="child in node.children"
      :key="child.id"
      :level="level + 1"
      :node="child"
    ></menu-tree-node-preview>
  </ul>
</li>
```

```css
.item {
  display: flex;
  height: 26px;
  padding-right: 10px;
  font-size: 12px;
  font-weight: 400;
  line-height: 26px;
  color: #333;
  transition: background-color .3s;

  i {
    font-size: 12px;
  }

  .icon {
    width: 15px;
    height: 100%;
    text-align: center;
    transition: all .3s;
  }

  .text {
    width: calc(100% - 67px);
    height: 100%;
    overflow: hidden;
    text-decoration: none;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  .button {
    display: none;
    width: 52px;
    height: 100%;
    text-align: right;
    transition: all .3s;

    i + i {
      margin-left: 8px;
    }
  }
}

.item:hover {
  color: #316ce5;
  background-color: #eaeaea;

  .button {
    display: block;
  }
}

[aria-haspopup="true"][aria-level="1"] > a,[aria-haspopup="true"][aria-level="1"] > .custom-tree-eidt-input {
  padding-left: 10px;
}

[aria-haspopup="true"][aria-level="2"] > a,[aria-haspopup="true"][aria-level="2"] > .custom-tree-eidt-input {
  padding-left: calc(10px + 15px * 1);
}

[aria-haspopup="true"][aria-level="3"] > a,[aria-haspopup="true"][aria-level="3"] > .custom-tree-eidt-input {
  padding-left: calc(10px + 15px * 2);
}

[aria-haspopup="true"][aria-level="4"] > a,[aria-haspopup="true"][aria-level="4"] > .custom-tree-eidt-input {
  padding-left: calc(10px + 15px * 3);
}

[aria-haspopup="false"][aria-level="1"] > a,[aria-haspopup="false"][aria-level="1"] > .custom-tree-eidt-input {
  padding-left: 25px;
}

[aria-haspopup="false"][aria-level="2"] > a,[aria-haspopup="false"][aria-level="2"] > .custom-tree-eidt-input {
  padding-left: calc(25px + 15px * 1);
}

[aria-haspopup="false"][aria-level="3"] > a,[aria-haspopup="false"][aria-level="3"] > .custom-tree-eidt-input {
  padding-left: calc(25px + 15px * 2);
}

[aria-haspopup="false"][aria-level="4"] > a,[aria-haspopup="false"][aria-level="4"] > .custom-tree-eidt-input {
  padding-left: calc(25px + 15px * 3);
}

[aria-expanded="false"] > [role="group"],[aria-haspopup="false"] > a .icon {
  display: none;
}

[aria-haspopup="false"] > a .text {
  width: calc(100% - 52px);
}

[aria-level="3"] > a .button .icon-tianjia {
  display: none;
}

[aria-expanded="true"] > a .icon {
          transform: rotate(90deg);

      -ms-transform: rotate(90deg);
     -moz-transform: rotate(90deg);
  -webkit-transform: rotate(90deg);
       -o-transform: rotate(90deg);
}

```

```javascript
// 收起、展开事件
nodeClick(e) {
  const liElement = e.currentTarget.parentElement;
  const expanded = liElement.getAttribute('aria-expanded');
  liElement.setAttribute('aria-expanded', expanded === 'true' ? 'false' : 'true');
}
// 处理菜单数据
handleMenuData() {
  const data = [
    {
      id: '1',
      title: '产品介绍',
      content: '',
      type: 'menu',
      pid: '',
      createTime: '2019-12-17 00:00:00',
      createUser: '马志礼',
      updateTime: '2019-12-17 00:00:00',
      updateUser: '马志礼',
    },
    {
      id: '2',
      title: '什么是云容器引擎',
      content: '',
      type: 'menu',
      pid: '1',
      createTime: '2019-12-17 00:00:00',
      createUser: '马志礼',
      updateTime: '2019-12-17 00:00:00',
      updateUser: '马志礼',
    },
    {
      id: '3',
      title: '容器全栈产品',
      content: '',
      type: 'menu',
      pid: '1',
      createTime: '2019-12-17 00:00:00',
      createUser: '马志礼',
      updateTime: '2019-12-17 00:00:00',
      updateUser: '马志礼',
    },
    {
      id: '4',
      title: '产品优势',
      content: '',
      type: 'menu',
      pid: '1',
      createTime: '2019-12-17 00:00:00',
      createUser: '马志礼',
      updateTime: '2019-12-17 00:00:00',
      updateUser: '马志礼',
    },
    {
      id: '5',
      title: '与其它云服务关系',
      content: '',
      type: 'menu',
      pid: '1',
      createTime: '2019-12-17 00:00:00',
      createUser: '马志礼',
      updateTime: '2019-12-17 00:00:00',
      updateUser: '马志礼',
    },
    {
      id: '6',
      title: '百度云',
      content: '',
      type: 'menu',
      pid: '5',
      createTime: '2019-12-17 00:00:00',
      createUser: '马志礼',
      updateTime: '2019-12-17 00:00:00',
      updateUser: '马志礼',
    },
    {
      id: '7',
      title: '腾讯云',
      content: '',
      type: 'menu',
      pid: '5',
      createTime: '2019-12-17 00:00:00',
      createUser: '马志礼',
      updateTime: '2019-12-17 00:00:00',
      updateUser: '马志礼',
    },
    {
      id: '8',
      title: '华为云',
      content: '',
      type: 'menu',
      pid: '5',
      createTime: '2019-12-17 00:00:00',
      createUser: '马志礼',
      updateTime: '2019-12-17 00:00:00',
      updateUser: '马志礼',
    },
    {
      id: '9',
      title: '阿里云',
      content: '',
      type: 'menu',
      pid: '5',
      createTime: '2019-12-17 00:00:00',
      createUser: '马志礼',
      updateTime: '2019-12-17 00:00:00',
      updateUser: '马志礼',
    },
    {
      id: '10',
      title: '特性指南',
      content: '',
      type: 'menu',
      pid: '',
      createTime: '2019-12-17 00:00:00',
      createUser: '马志礼',
      updateTime: '2019-12-17 00:00:00',
      updateUser: '马志礼',
    },
    {
      id: '11',
      title: '控制台指南',
      content: '',
      type: 'menu',
      pid: '',
      createTime: '2019-12-17 00:00:00',
      createUser: '马志礼',
      updateTime: '2019-12-17 00:00:00',
      updateUser: '马志礼',
    },
    {
      id: '12',
      title: '工具指南',
      content: '',
      type: 'menu',
      pid: '',
      createTime: '2019-12-17 00:00:00',
      createUser: '马志礼',
      updateTime: '2019-12-17 00:00:00',
      updateUser: '马志礼',
    },
    {
      id: '13',
      title: '快速入门',
      content: '',
      type: 'menu',
      pid: '',
      createTime: '2019-12-17 00:00:00',
      createUser: '马志礼',
      updateTime: '2019-12-17 00:00:00',
      updateUser: '马志礼',
    },
    {
      id: '14',
      title: '价格说明',
      content: '',
      type: 'menu',
      pid: '',
      createTime: '2019-12-17 00:00:00',
      createUser: '马志礼',
      updateTime: '2019-12-17 00:00:00',
      updateUser: '马志礼',
    },
  ];
  this.menuList = this.flat2Tree(data);
}
// 扁平数组转为 树结构 数组
flat2Tree(paramList) {
  const data = JSON.parse(JSON.stringify(paramList));
  data.forEach((item)=> {
    // 子元素列表
    item.children = [];
  });
  const parents = data.filter((item)=> item.pid === '');
  const children = data.filter((item)=> item.pid !== '');
  const translator = (parents, children)=> {
    parents.forEach((parent)=> {
      children.forEach((current, index)=> {
        if (current.pid === parent.id) {
          const temp = JSON.parse(JSON.stringify(children));
          temp.splice(index, 1);
          translator([current], temp);
          parent.children.push(current);
        }
      });
    });
  };
  translator(parents, children);
  return JSON.parse(JSON.stringify(parents));
}
```