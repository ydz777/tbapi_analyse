### 非常规参数取值记录

淘宝直通车API：https://subway.simba.taobao.com/

| 参数      | 取值                                                       |
| --------- | ---------------------------------------------------------- |
| sessionId | localStorage.getItem('sid')                                |
| token     | https://subway.simba.taobao.com/bpenv/getLoginUserInfo.htm |

淘宝引力魔方API：https://tuijian.taobao.com/

| 参数         | 取值                                                         |
| ------------ | ------------------------------------------------------------ |
| csrfID       | https://tuijian.taobao.com/api2/member/getInfo.json          |
| dynamicToken | https://g.alicdn.com/mm/display/20220311.140658.727/display/services/jsvm.js |



```js
module.exports = function(n, t, r) {
            n = n || "",
            t = t || 2;
            var e, o, s, u, i, jsvmportal_0_1 = function() {
                var inout = arguments, retval;
                return jsvm_this_run(function() {
                    return eval(arguments[0])
                }, 0),
                retval
            };
            return jsvm_this_run(function() {
                return eval(arguments[0])
            }, 1),
            "" + e(u) + e(i)
}
// dynamicToken 计算方法 
// seedToken,pin,csrfID 都来源于这个接口 https://tuijian.taobao.com/api2/member/getInfo.json
var dynamicToken = jsvmfuc(seedToken, pin, timeStamp)

```

### 千牛MTOP接口

```js


//获取收货地址
await window.lib.mtop.request({
    api: 'mtop.taobao.mbis.getdeliveraddrlist',
    v: '1.0',
    data: {},
  });

//评价
await window.lib.mtop.request({
    api: 'mtop.taobao.rate.detaillist.get',
    v: '4.0',
    data: {auctionNumId:'574484564204',pageSize:50,pageNo:1,hasPic:1,foldFlag:0,rateType:""},
  });

//视频
await window.lib.mtop.request({
    api: 'mtop.taobao.cloudvideo.video.queryForH5',
    v: '1.0',
    data: {videoId:'224731699946',from:'detail'},
  });

//主图
await window.lib.mtop.request({
    api: 'mtop.taobao.detail.getdetail',
    v: '6.0',
    data: {itemNumId:'574484564204'},
});

//详情图
await window.lib.mtop.request({
    api: 'mtop.wdetail.getItemDescx',
    v: '4.1',
    data: {item_num_id:'574484564204'},
  });



//商品信息
await QN.app.invoke({
    api: 'invokeMTopChannelService',
    query: {
      method: 'mtop.tmall.sell.pc.manage.async',
      param: {"url":"/tmall/manager/table.htm?tab=all","jsonBody":"{\"tab\":\"all\",\"pagination\":{\"current\":1,\"pageSize\":20},\"filter\":{},\"table\":{}}"},
      httpMethod: 'post',
      version: '1.0',
    },
  }); 
//问大家
await QN.app.invoke({
    api: 'invokeMTopChannelService',
    query: {
      method: 'mtop.rm.sellercenter.ask.list',
      param: {"jsonBody":"{\"pagination\":{\"current\":1,\"pageSize\":10},\"hasAnswer\":1,\"bizType\":200}"},
      httpMethod: 'post',
      version: '1.0',
    },
  }); 
//店铺评价信息
await QN.app.invoke({
    api: 'invokeMTopChannelService',
    query: {
      method: 'mtop.rm.sellercenter.list.data.pc',
      param: {"jsonBody":"{\"pageType\":\"rateWait4PC\",\"pagination\":{\"current\":1,\"pageSize\":20}}"},
      httpMethod: 'post',
      version: '1.0',
    },
  }); 
//千牛快捷短语
await QN.app.invoke({
    api: 'invokeMTopChannelService',
    query: {
      method: 'mtop.taobao.qianniu.quickphrase.get',
      param: {from:'',version:1.0},
      httpMethod: 'post',
      version: '1.0',
    },
  }); 

//解密收货人信息
await imsdk.invoke('application.invokeMTopChannelService', {
    method: 'mtop.cainiao.consign.order.decryptorder',
    param: {"tradeId":"订单号","channelCode":"SELLER_CENTER_PC"},
    httpMethod: 'post',
    version: '1.0'
});

// 修改订单收货地址
await QN.app.invoke({
    api: 'invokeMTopChannelService',
    query: {
      method: 'mtop.cainiao.consign.tborder.memoflag.update',
      param:{
	{"receiverAddressJson":"{\"address\":\"丈八沟街道科技七路香榭御澄底商雅兰婷\",\"areaId\":\"610113\",\"areaName\":\"雁塔区\",\"cityId\":\"610100\",\"cityName\":\"西安市\",\"countryId\":1,\"post\":\"000000\",\"provId\":\"610000\",\"provName\":\"陕西省\",\"townId\":\"610113007\",\"townName\":\"丈八沟街道\"}","receiverJson":"{\"userName\":\"姓名\",\"mobilePhone\":\"手机\"}","tradeId":"订单号","pageStatus":4,"channelCode":"SELLER_CENTER_PC"}
      },
      httpMethod: 'post',
      version: '1.0',
    },
  }); 

// 修改订单卖家备注
await QN.app.invoke({
    api: 'invokeMTopChannelService',
    query: {
      method: 'mtop.cainiao.consign.tborder.memoflag.update',
      param:{
	"tradeId":"订单号","memo":"做好发货","flag":1,"channelCode":"SELLER_CENTER_PC"
      },
      httpMethod: 'post',
      version: '1.0',
    },
  }); 


// 好友列表
await QN.app.invoke({
    api: 'invokeMTopChannelService',
    query: {
      method: 'mtop.taobao.wireless.amp2.im.relation.rebase',
      param:{
	"accessKey": "qianniu-pc",
	"accessSecret": "qianniu-pc-secret","accountType": "3",
	"bottomOffset": 100,
	"topOffset": 100
},
      httpMethod: 'post',
      version: '1.0',
    },
  }); 

//千牛店铺子账号在线状态
await QN.app.invoke({
    api: 'invokeMTopChannelService',
    query: {
      method: 'mtop.taobao.qianniu.cloudkefu.accountstatus.getbyid',
      param: {pageSize: 100},
      httpMethod: 'post',
      version: '1.0',
    },
  }); 

//专属客服卡片
await QN.app.invoke({
    api: 'invokeMTopChannelService',
    query: {
      method: 'mtop.taobao.qianniu.bcpush.send.subscribecard',
      param: {"subscriberNick":"淘宝昵称"},
      httpMethod: 'post',
      version: '1.0',
    },
  }); 

//添加好友
await QN.app.invoke({
    api: 'invokeMTopChannelService',
    query: {
      method: 'mtop.taobao.wireless.amp2.im.relation.addcontact',
      param:{
	"accessKey": "qianniu-pc",
	"accessSecret": "qianniu-pc-secret",
	"accountType": "3",
	"contactReq": "{\"targetAccountId\":\"淘宝UserId\",\"targetAccountType\":\"3\",\"targetNickName\":\"\",\"targetRemarkName\":\"\",\"groupId\":0,\"bizType\":\"-1\",\"relationType\":0,\"ext\":{\"msg\":\"验证信息\"}}"
},
      httpMethod: 'post',
      version: '1.0',
    },
  }); 


//删除好友
await QN.app.invoke({
    api: 'invokeMTopChannelService',
    query: {
      method: 'mtop.taobao.wireless.amp2.im.relation.deletecontact',
      param: {"accessKey":"qianniu-pc","contactlist":"[{\"targetAccountId\":\"淘宝UserId\",\"targetAccountType\":3,\"bizType\":\"-1\",\"relationType\":0}]","accessSecret":"qianniu-pc-secret","accountType":"3"},
      httpMethod: 'post',
      version: '1.0',
    },
  }); 
  
 //标星 
await QN.app.invoke({
    api: 'invokeMTopChannelService',
    query: {
      method: 'mtop.taobao.qianniu.airisland.tag.batch.update',
      param:{"context":"{\"bizDomain\":\"taobao\"}","tagUpdateParams":"[{\"tagCode\":\"TOP_TYPE_RED\",\"targetId\":\"1597305140\",\"bizExt\":\"{}\",\"entityType\":0,\"bizDomain\":\"taobao\",\"groupCode\":\"QIANNIU_STAR\",\"updateType\":0}]","tenantId":"QIANNIU_RECEPTION"},

      httpMethod: 'post',
      version: '2.0',
    },
  }); 

//订单物流信息
await QN.app.invoke({
    api: 'invokeMTopChannelService',
    query: {
      method: 'mtop.cainiao.cilogistics.smart.customer.logistics.detail',
      param:{"tradeId":"订单号","sellerId":"0"},

      httpMethod: 'post',
      version: '1.0',
    },
  }); 

//快捷短语
await QN.app.invoke({
    api: 'invokeMTopChannelService',
    query: {
      method: 'mtop.taobao.qianniu.quickphrase.get',
      param: {from:'',version:1.0},
      httpMethod: 'post',
      version: '1.0',
    },
  }); 
// 核对订单卡片
imsdk.invoke('application.invokeMTopChannelService', {
            method: 'mtop.taobao.bcpush.order.check.card.send',
            param:{bizOrderId:'订单号',buyerNick:'淘宝昵称'},
            httpMethod: 'post',
            version: '1.0'
        });
await QN.app.invoke({
    api: 'invokeMTopChannelService',
    query: {
      method: 'mtop.taobao.bcpush.order.check.detail.card.send',
      param: {"bizOrderId":"订单号","buyerId":"买家Id"},
      httpMethod: 'post',
      version: '1.0',
    },
  }); 
//邀请下单
await imsdk.invoke('application.invokeMTopChannelService', {
    method: 'mtop.taobao.qianniu.airisland.invite.order.send',
    param: {
        buyerNick: '淘宝昵称',
        itemProps: JSON.stringify([{
            itemId: 商品id,
            skuId: 'skuid',
            quantity: 数量,
            context: {}
        }])
    },
    httpMethod: 'post',
    version: '1.0'
});
//邀请下单网页链接
http://h5.m.taobao.com/awp/base/order.htm?itemId=581893384636&quantity=50&buyNow=true&skuId=4068777279306&spm=a21ddn.22796030a21ddn.23524755.581893384636
//转接 到个人
imsdk.invoke('application.invokeMTopChannelService', {
            method: 'mtop.taobao.qianniu.cloudkefu.forward',
            param:{"buyerId":buyerid,"toId":toid,"reason":"","options":"{\"appCid\":\"ccode\",\"buyerDomain\":\"cntaobao\",\"loginDomain\":\"cntaobao\"}"},
            httpMethod: 'post',
            version: '3.0'
        });
// 转接 到分组
imsdk.invoke('application.invokeMTopChannelService', {
            method: 'mtop.taobao.qianniu.cloudkefu.forward',
            param:{\"forwardType\":2,\"charset\":\"utf-8\",\"groupId\":groupid,\"exceptUsers\":\"cntaobaosendernick\",\"loginDomain\":\"cntaobao\",\"buyerDomain\":\"cntaobao\",\"appCid\":\"ccode\"}"},
            httpMethod: 'post',
            version: '3.0'
        });
	
//自助锁单
imsdk.invoke('application.invokeMTopChannelService', {
            method: 'mtop.taobao.gearfactory.order.intercept',
            param:{bizOrderId:"2133960085351304051",fromNick:"itoqc0665",buyerNick:'vrkelun3258',triggerType:"airisland",subOrderIds:'["2133960085351304051"]'},
            httpMethod: 'post',
            version: '1.0'
});
//转接的客服分组信息，包含客服信息
imsdk.invoke('application.invokeMTopChannelService', {
            method: 'mtop.taobao.qianniu.cloudkefu.dispatchgroups.get',
            httpMethod: 'post',
            version: '2.0'
        });

//发送群消息
imsdk.invoke('application.invokeMTopChannelService', {
            method: 'mtop.taobao.wireless.amp2.im.message.send',
            param:{"bizType":"301","entityType":"G","accessKey":"qianniu-pc","accessSecret":"qianniu-pc-secret","sdkVersion":"1.0.0","messages":"[{\"templateData\":\"{\\\"text\\\":\\\"msgtext\\\"}\",\"templateId\":101,\"bizUnique\":\"0_G_2155747714#3_1642477787905140#3_1650955165585_36500\",\"summary\":\"\",\"ext\":{\"sender_nick\":\"uid\",\"bizChainID\":null,\"receiver_nick\":\"\",\"messageSource\":2},\"extraAttr\":{}}]","entityId":"0_G_2155747714#3_1642478076769_0_1597305140#3"},
            httpMethod: 'post',
            version: '1.0'
        });
	
//拦截发货 主订单
imsdk.invoke('application.invokeMTopChannelService', {
            method: 'mtop.taobao.gearfactory.order.interceptallV2',
            param:{bizOrderId:'212531990405500000761',fromNick:"",buyerNick:'vrkelun3258',"triggerType":"airisland"},
            httpMethod: 'post',
            version: '1.0'
        });
//拦截发货 子订单
imsdk.invoke('application.invokeMTopChannelService', {
            method: 'mtop.taobao.gearfactory.order.intercept',
            param:{bizOrderId:"21332364587351304051",fromNick:"itoqc0665",buyerNick:'vrkelun3258',triggerType:"airisland",subOrderIds:'["21339607498789794051"]'},
            httpMethod: 'post',
            version: '1.0'
        });
//用户查询 用来nick 转成 userid
imsdk.invoke('application.invokeMTopChannelService', {
            method: 'mtop.taobao.wireless.amp2.im.relation.search',
            param: {"accessKey":"qianniu-pc","accessSecret":"qianniu-pc-secret","accountType":"3","searchKey":"xxx旗舰店"},
            httpMethod: 'post',
            version: '1.0'
        });
```


右键点击Finder选择前往文件夹, 输入:

~/Library/Group Containers/K36BKF7T3D.group.com.apple.configurator/Library/Caches/Assets/TemporaryItems/MobileApps/
