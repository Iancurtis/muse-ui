<template>
<mu-drawer @close="handleClose" :open="open" :docked="docked" class="app-drawer" :zDepth="1">
  <mu-appbar class="exmaples-nav-appbar" :zDepth="0">
    <a class="exmaples-appbar-title" @click="handleMenuChange('#/index')" href="#/index" style="display:inline-block;">Muse-UI</a>
    <mu-badge content="alpha" class="exmaples-version" secondary/>
  </mu-appbar>
  <mu-divider/>
  <mu-flexbox class="mu-version-box" align="center">
    <span class="mu-version-text">Version: </span>
    <mu-dropDown-menu :value="version" @change="handleVersionChange" v-if="versions.length > 0">
      <mu-menu-item v-for="vtext in versions" :value="vtext" :title="vtext"/>
    </mu-dropDown-menu>
  </mu-flexbox>
  <mu-list @change="handleMenuChange" :value="menuVal">
    <mu-list-item title="快速开始" toggleNested>
      <mu-list-item href="#/install" value="#/install" slot="nested" title="安装"/>
      <mu-list-item href="#/usage" value="#/usage" slot="nested" title="使用"/>
    </mu-list-item>
    <mu-list-item title="个性定制" toggleNested>
      <mu-list-item slot="nested" href="#/theme" value="#/theme" title="主题"/>
      <mu-list-item slot="nested" href="#/colors" value="#/colors" title="颜色"/>
    </mu-list-item>

    <mu-list-item title="基础组件" toggleNested>
      <mu-sub-header slot="nested" class="exmaples-nav-sub-header">Material Design</mu-sub-header>
      <mu-list-item slot="nested" href="#/appbar" value="#/appbar" title="App Bar"/>
      <mu-list-item slot="nested" href="#/autoComplete" value="#/autoComplete" title="Auto Complete"/>
      <mu-list-item slot="nested" href="#/avatar" value="#/avatar" title="Avatar"/>
      <mu-list-item slot="nested" href="#/badge" value="#/badge" title="Badge"/>
      <mu-list-item slot="nested" href="#/bottomNav" value="#/bottomNav" title="Bottom Navigation"/>
      <mu-list-item slot="nested" href="#/bottomSheet" value="#/bottomSheet" title="Bottom Sheet"/>
      <mu-list-item slot="nested" title="Buttons" toggleNested>
        <mu-list-item slot="nested" href="#/flatButton" value="#/flatButton" title="Flat Button"></mu-list-item>
        <mu-list-item slot="nested" href="#/raisedButton" value="#/raisedButton" title="Raised Button"></mu-list-item>
        <mu-list-item slot="nested" href="#/iconButton" value="#/iconButton" title="Icon Button"></mu-list-item>
        <mu-list-item slot="nested" href="#/floatButton" value="#/floatButton" title="Floating Action Button"></mu-list-item>
      </mu-list-item>
      <mu-list-item slot="nested" href="#/card" value="#/card" title="Card"/>
      <mu-list-item slot="nested" href="#/chip" value="#/chip" title="Chip"/>
      <mu-list-item slot="nested" href="#/datePicker" value="#/datePicker" title="Date Picker"/>
      <mu-list-item slot="nested" href="#/dialog" value="#/dialog" title="Dialog"/>
      <mu-list-item slot="nested" href="#/divider" value="#/divider" title="Divider"/>
      <mu-list-item slot="nested" href="#/drawer" value="#/drawer" title="Drawer"/>
      <mu-list-item slot="nested" href="#/gridList" value="#/gridList" title="Grid List"/>
      <mu-list-item slot="nested" href="#/icon" value="#/icon" title="Icon"/>
      <mu-list-item slot="nested" href="#/list" value="#/list" title="List"/>
      <mu-list-item slot="nested" title="Menus" toggleNested>
        <mu-list-item slot="nested" href="#/menu" value="#/menu" title="Menu"/>
        <mu-list-item slot="nested" href="#/iconMenu" value="#/iconMenu" title="Icon Menu"/>
        <mu-list-item slot="nested" href="#/dropDownMenu" value="#/dropDownMenu" title="DropDown Menu"/>
      </mu-list-item>
      <mu-list-item slot="nested" href="#/paper" value="#/paper" title="Paper"/>
      <mu-list-item slot="nested" href="#/popover" value="#/popover" title="Popover"/>
      <mu-list-item slot="nested" title="Progress" toggleNested>
        <mu-list-item slot="nested" href="#/linearProgress" value="#/linearProgress" title="Linear Progress"/>
      </mu-list-item>
      <mu-list-item slot="nested" href="#/selectField" value="#/selectField" title="Select Field"/>
      <mu-list-item slot="nested" title="Selection Controls" toggleNested>
        <mu-list-item slot="nested" href="#/checkbox" value="#/checkbox" title="Checkbox"/>
        <mu-list-item slot="nested" href="#/radio" value="#/radio" title="Radio"/>
        <mu-list-item slot="nested" href="#/switch" value="#/switch" title="Switch"/>
      </mu-list-item>
      <mu-list-item slot="nested" href="#/slider" value="#/slider" title="Slider"/>
      <mu-list-item slot="nested" href="#/snackbarToast" value="#/snackbarToast" title="SnackBar & Toast"/>
      <mu-list-item slot="nested" href="#/stepper" value="#/stepper" title="Stepper"/>
      <mu-list-item slot="nested" href="#/subHeader" value="#/subHeader" title="Sub Header"/>
      <mu-list-item slot="nested" href="#/table" value="#/table" title="Table"/>
      <mu-list-item slot="nested" href="#/tabs" value="#/tabs" title="Tabs"/>
      <mu-list-item slot="nested" href="#/textField" value="#/textField" title="Text Field"/>
      <mu-list-item slot="nested" href="#/timePicker" value="#/timePicker" title="Time Picker"/>
      <mu-list-item slot="nested" href="#/tooltip" value="#/tooltip" title="Tooltip"/>
      <mu-sub-header slot="nested" class="exmaples-nav-sub-header">Others</mu-sub-header>
      <mu-list-item slot="nested" href="#/contentBlock" value="#/contentBlock" title="Content Block"/>
      <mu-list-item slot="nested" href="#/flexbox" value="#/flexbox" title="Flex Box"/>
      <mu-list-item slot="nested" href="#/grid" value="#/grid" title="Grid"/>
      <mu-list-item slot="nested" href="#/infiniteScroll" value="#/infiniteScroll" title="Infinite Scroll"/>
      <mu-list-item slot="nested" href="#/picker" value="#/picker" title="Picker"/>
      <mu-list-item slot="nested" href="#/popup" value="#/popup" title="Popup"/>
      <mu-list-item slot="nested" href="#/refreshControl" value="#/refreshControl" title="Refresh Control"/>
    </mu-list-item>
    <mu-list-item title="更多信息" toggleNested>
      <mu-list-item slot="nested" title="更新日志" href="#/changeLog" value="#/changeLog"/>
      <mu-list-item slot="nested" title="贡献指南" href="#/contributing" value="#/contributing"/>
    </mu-list-item>
  </mu-list>
  <mu-divider/>
  <mu-sub-header>资源</mu-sub-header>
  <mu-list>
    <mu-list-item href="https://github.com/museui/muse-ui" target="_blank" title="GitHub"/>
    <mu-list-item href="http://vuejs.org/" target="_blank" title="Vue"/>
    <mu-list-item href="https://material.google.com/" target="_blank" title="Material Design"/>
    <mu-list-item href="http://www.material-ui.com/" target="_blank" title="Material-UI"/>
  </mu-list>
</mu-drawer>
</template>

<script>
import packageJson from '../../package.json'
export default {
  props: {
    open: {
      type: Boolean,
      default: true
    },
    docked: {
      type: Boolean,
      default: true
    }
  },
  data () {
    return {
      menuVal: '#/',
      version: packageJson.version,
      versions: []
    }
  },
  methods: {
    handleVersionChange (val) {
      if (val !== this.version) {
        var url = this.versions.indexOf(val) === 0 ? '/' : '/' + val
        window.open(url)
      }
    },
    handleClose () {
      this.$emit('close')
    },
    handleMenuChange (val) {
      this.menuVal = val
      this.$emit('change', val)
    }
  },
  mounted () {
    this.menuVal = window.location.hash
    window.addEventListener('hashchange', () => {
      this.menuVal = window.location.hash
    })
    var xhr = new window.XMLHttpRequest()
    xhr.open('GET', '/version.json', true)
    xhr.onload = () => {
      if (xhr.readyState === 4) {
        if (xhr.status === 200) {
          this.versions = JSON.parse(xhr.responseText)
        } else {
          console.error(xhr.statusText)
        }
      }
    }
    xhr.send()
  }
}
</script>

<style lang="less">
@import "../../src/styles/vars.less";
.exmaples-drawer{
  box-shadow: none;
  border-right: 1px solid @borderColor;
}

.exmaples-nav-appbar.mu-appbar{
  background-color: @dialogBackgroundColor;
  color: @secondaryTextColor;
}
.exmaples-appbar-title{
  color: @secondaryTextColor;
}

.exmaples-version {
  margin-left: 10px;
  align-self: flex-start;
}

.exmaples-nav-sub-header {
  padding-left: 34px;
}

.mu-version-box{
  height: 48px;
  margin-top: 8px;
  padding-left: 16px;
  padding-right: 16px;
}
.mu-version-text {
  font-size: 16px;
  margin-top: 8px;
}
</style>
