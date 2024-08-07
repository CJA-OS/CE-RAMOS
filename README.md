<h1 align="center">
  <br>
<img src="https://avatars.githubusercontent.com/u/126374901?s=400&u=8a44ae595278573eac68b75ecf5f129defac9449&v=4" width="150"/>
  <br>
  CE-RAMOS
  <br>
</h1>

<h4 align="center">👉一个致力于模仿原版Win11界面以及体验的PE</h4>

<p align="center">原生任务栏和开始菜单、Windows11界面、全局暗黑、Rectify11主题及界面、自研的全新插件、兼容Edgeless插件、兼容HotPE模块、不依赖PECMD(当加载插件或模块时会按需释放)、使用原生登录，开机默认登录Adminstrator、DX12支持、MTP支持...</p>

<p align="center">
  <a href="https://ce-ramos.cn">首页</a> -
  <a href="https://docs.ce-ramos.cn">文档</a> -
  <a href="https://files.ce-ramos.cn">下载站</a>  -
</p>

## 下载

官方文件下载站：https://files.ce-ramos.cn/%E4%B8%8B%E8%BD%BD/CE-RAMOS%E6%96%87%E4%BB%B6<div>

123盘链接(分流)：https://www.123pan.com/s/5ZD9-OpJfd.html<div>
Github(不推荐)：本存储库Releases<div>

## 使用

下载PE镜像后写入U盘或使用 <a href="https://files.ce-ramos.cn/d/%E4%B8%8B%E8%BD%BD/CE-RAMOS%E6%96%87%E4%BB%B6/CE-RAMOS%20Hub/CE-RAMOS%20Hub.exe">CE-RAMOS Hub (单击立即下载)</a>

## CE-RAMOS版本信息<br><br>
#### UWP版本：
<Badge type="tip">版本：{{ iso_version }}</Badge> <Badge type="info">作者：CE-RAMOS开发团队</Badge> <Badge type="warning">版本类型：Stable</Badge>

#### 非UWP版本：
* 与UWP相同母盘制作的内核
* 使用WinXShell、StartAllBack等第三方组件，占用更低，速度更快
<Badge type="tip">版本：{{ iso_second_version }}</Badge> <Badge type="info">作者：CE-RAMOS开发团队</Badge> <Badge type="warning">版本类型：Stable</Badge>

## 敬请期待
基于Tauri、TypeScript、Vite、React为底层的新版CE-RAMOS Hub正在开发中，敬请期待！😄

<script>  
export default {  
  data() {  
    return {  
      iso_version: '获取中...',
      iso_second_version: '获取中...',
      hub_version: '获取中...'  
    };  
  },  
  methods: {  
    fetchInfo() {  
      fetch('https://api.ce-ramos.cn/GetInfo/')  
        .then(response => {  
          if (!response.ok) {  
            throw new Error('Network response was not ok');  
          }  
          return response.json();  
        })  
        .then(data => {  
          this.iso_version = data.data.iso_version === 'null' ? '获取失败' : `CE-RAMOS ${data.data.iso_version} Pro (UWP)`;
          this.iso_second_version = data.data.iso_second_version === 'null' ? '获取失败' : `CE-RAMOS ${data.data.iso_second_version} Pro`;   
          this.hub_version = data.data.hub_version === 'null' ? '获取失败' : `CE-RAMOS Hub+${data.data.hub_version}`;  
        })  
        .catch(error => {  
          console.error('There was a problem with your fetch operation:', error);  
          this.iso_version = '获取失败'; 
          this.iso_second_version = '获取失败'; 
          this.hub_version = '获取失败';  
        });  
    }  
  },  
  mounted() {  
    this.fetchInfo();  
  }  
};  
</script>  
