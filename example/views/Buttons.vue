<template>
  <div>
    <h1>基础按钮</h1>
    <i class="icon iconfont icon-arrowdownb"></i>
    <h-button>Default</h-button>
    <h-button type="primary">Primary</h-button>
    <h-button type="ghost">Ghost</h-button>
    <h-button type="dashed">Dashed</h-button>
    <h-button type="text">Text</h-button>
    <br><br>
    <h-button type="info">信息按钮</h-button>
    <h-button type="success">成功按钮</h-button>
    <h-button type="warning">警告按钮</h-button>
    <h-button type="error">错误按钮</h-button>
    <h1>带图标按钮</h1>
    <h-icon name="search"></h-icon>
    <h-button type="primary" shape="circle" icon="search"></h-button>
    <h-button type="primary" icon="search">搜索</h-button>
    <h-button type="primary" shape="circle" icon="search">搜索</h-button>
    <h-button type="primary" shape="circle">圆角按钮</h-button>
    <br><br>
    <h-button type="ghost" shape="circle" icon="search"></h-button>
    <h-button type="ghost" icon="search">搜索</h-button>
    <h-button type="ghost" shape="circle" icon="search">搜索</h-button>
    <h-button type="ghost" shape="circle">圆角按钮</h-button>
    <h1>按钮尺寸</h1>
    <h-button type="primary" size="large">Large</h-button>
    <h-button type="primary">Default</h-button>
    <h-button type="primary" size="small">Small</h-button>
    <br><br>
    <h-button type="primary" shape="circle" size="large">Large</h-button>
    <h-button type="primary" shape="circle">Default</h-button>
    <h-button type="primary" shape="circle" size="small">Small</h-button>
    <h1>长按钮</h1>
    <h-button type="success" long>确认提交</h-button>
    <br><br>
    <h-button type="error" long>确认删除</h-button>
    <h1>不可用状态</h1>
    <h-button>Default</h-button>
    <h-button disabled>Default(Disabled)</h-button>
    <br><br>
    <h-button type="primary">Primary</h-button>
    <h-button type="primary" disabled>Primary(Disabled)</h-button>
    <br><br>
    <h-button type="ghost">Ghost</h-button>
    <h-button type="ghost" disabled>Ghost(Disabled)</h-button>
    <br><br>
    <h-button type="dashed">Dashed</h-button>
    <h-button type="dashed" disabled>Dashed(Disabled)</h-button>
    <br><br>
    <h-button type="text">Text</h-button>
    <h-button type="text" disabled>Text(Disabled)</h-button>
    <h1>按钮组---基本</h1>
    <h-button-group>
        <h-button>取消</h-button>
        <h-button type="primary">确定</h-button>
    </h-button-group>
    <h-button-group>
        <h-button disabled>昨日</h-button>
        <h-button disabled>今日</h-button>
        <h-button disabled>明日</h-button>
    </h-button-group>
    <h-button-group>
        <h-button type="primary">L</h-button>
        <h-button>M</h-button>
        <h-button type="ghost">M</h-button>
        <h-button type="dashed">R</h-button>
    </h-button-group>
    <br><br>
    <h4>配合图标</h4>
    <br><br>
    <h-button-group>
      <h-button type="primary">
          <h-icon name="return"></h-icon>
          前进
      </h-button>
      <h-button type="primary">
          后退
          <h-icon name="enter"></h-icon>
      </h-button>
    </h-button-group>
    <h-button-group>
       <h-button type="primary" icon="return"></h-button>
       <h-button type="primary" icon="enter"></h-button>
     </h-button-group>
     <h-button-group>
       <h-button type="ghost" icon="emoji"></h-button>
       <h-button type="ghost" icon="empty"></h-button>
       <h-button type="ghost" icon="enterinto"></h-button>
       <h-button type="ghost" icon="feedback_fill"></h-button>
     </h-button-group>
     <br><br>
     <h4>圆角</h4>
    <br><br>
    <h-button-group shape="circle">
        <h-button type="primary">
            <h-icon name="return"></h-icon>
            前进
        </h-button>
        <h-button type="primary">
            后退
            <h-icon name="enter"></h-icon>
        </h-button>
    </h-button-group>
    <h-button-group shape="circle">
        <h-button type="primary" icon="return"></h-button>
        <h-button type="primary" icon="enter"></h-button>
    </h-button-group>
    <h-button-group shape="circle">
        <h-button type="ghost" icon="emoji"></h-button>
        <h-button type="ghost" icon="empty"></h-button>
        <h-button type="ghost" icon="enterinto"></h-button>
        <h-button type="ghost" icon="feedback_fill"></h-button>
    </h-button-group>
    <br><br>
    <h4>尺寸</h4>
    <br><br>
    <h-button-group size="large">
        <h-button type="ghost">Large</h-button>
        <h-button type="ghost">Large</h-button>
    </h-button-group>
    <h-button-group>
        <h-button type="ghost">Default</h-button>
        <h-button type="ghost">Default</h-button>
    </h-button-group>
    <h-button-group size="small">
        <h-button type="ghost">Small</h-button>
        <h-button type="ghost">Small</h-button>
    </h-button-group>
    <br><br>
    <h-button-group size="large" shape="circle">
        <h-button type="ghost">Large</h-button>
        <h-button type="ghost">Large</h-button>
    </h-button-group>
    <h-button-group shape="circle">
        <h-button type="ghost">Default</h-button>
        <h-button type="ghost">Default</h-button>
    </h-button-group>
    <h-button-group size="small" shape="circle">
        <h-button type="ghost">Small</h-button>
        <h-button type="ghost">Small</h-button>
    </h-button-group>
    <h1>按钮组--垂直方向</h1>
    <h-button-group vertical>
        <h-button type="ghost" icon="emoji"></h-button>
        <h-button type="ghost" icon="empty"></h-button>
        <h-button type="ghost" icon="enterinto"></h-button>
        <h-button type="ghost" icon="feedback_fill"></h-button>
    </h-button-group>
    <h1>加载中按钮</h1>
    <h-button type="primary" :loading="true">加载中</h-button>
  </div>
</template>

<script>

export default {
  name: 'buttons',
  data() {
    return {
    }
  },
  methods:{
    btnClick(){
      alert('按钮被点击了！');
    }
  }
}
</script>
<style type="text/css">
</style>