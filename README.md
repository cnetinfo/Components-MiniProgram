# Components-MiniProgram
小程序组件

dialog使用
```HTML
<!--index.wxml-->
<dialog id='dialog' 
  title='修改价格' 
  content='原价：4500.00/元' 
  cancelText='取消' 
  confirmText='确定'
  bind:cancelEvent="_cancelEvent"  
  bind:confirmEvent="_confirmEvent">
  <view slot="input">
    <input placeholder="请输入要修改的价格" class="wx-input" auto-focus/>
  </view>
</dialog>
<button type="primary" bindtap="showDialog"> 弹框组件! </button>
```

```css
/**index.wxss**/
.wx-input{
  border-radius:30px; 
  border:1rpx solid #A5B1C3; 
  margin:10px 10%;
  line-height:45px; 
  padding:10px 0px
}
```

```Javascript
/**index.js**/
Page({
  /**
 * 生命周期函数--监听页面初次渲染完成
 */
  onReady: function () {
    //获得dialog组件
    this.dialog = this.selectComponent("#dialog");
  },

  showDialog(){
    this.dialog.showDialog();
  },

   //取消事件
  _cancelEvent(){
    console.log('你点击了取消');
    this.dialog.hideDialog();
  },
  //确认事件
  _confirmEvent(){
    console.log('你点击了确定');
    this.dialog.hideDialog();
  }
})
```
```Javascript
/**index.json**/
{
  "usingComponents": {
    "dialog": "../../components/dialog/dialog"
  }
}
```
效果图
![](https://github.com/cnetinfo/ImageLib/blob/master/projectImg/d1.png)  
![](https://github.com/cnetinfo/ImageLib/blob/master/projectImg/d2.png)  
![](https://github.com/cnetinfo/ImageLib/blob/master/projectImg/d3.png)  
