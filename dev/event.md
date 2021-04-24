# 事件系统
目前MCBBS Loader主分支上移植的MCBBS Extender事件并不能正常工作。无论如何，如果用户也安装了MCBBS Extender，你可以监听原生MCBBS Extender的事件，DiscuzAjaxPostFinished和DiscuzAjaxGetFinished发布在油猴脚本内部，无法监听。

<span style="color: brown">**情况有变：我们正在尝试修复这些问题**</span>

尽管此部分的内容未添加解释，但是你大概通过名字大概可以猜到这些事件的用处。

支持的MCBBS Extender事件如下：
- ThreadPreviewPreOpen  
- ThreadPreviewOpened  
- ThreadPreviewClosed  
- ThreadFlushStarted  
- ThreadFlushFinished  
- RateWindowPreOpen  
- RateWindowOpened  
- RateWindowClosed  
- ReplyWindowPreOpen  
- ReplyWindowOpened  
- ReplyWindowClosed  
- ReportWindowPreOpen  
- ReportWindowOpened  
- ReportWindowClosed  
- NewReplyAppended  
- ThreadsListLoadStart  
- ThreadsListLoadFinished  
- DiscuzAjaxPostFinished  
- DiscuzAjaxGetFinished  

Loader支持的事件如下：
- `DiscuzAjaxPrePost`
  在使用ajaxpost发出请求之前触发  
  - `callback(event)` 「可取消」  
    - `event` - 一个MCBBS.LoaderEvent实例  
	  - `formid`  
      - `showid`  
	  - `waitid`  
	  - `showidclass`  
	  - `submitbtn`  
	  - `recall`  
- `DiscuzAjaxPostPost` 
  在使用ajaxpost请求完成时触发  
  - `callback(event)`   
    - `event` - 一个MCBBS.LoaderEvent实例  
	  - `formid`  
      - `showid`  
	  - `waitid`  
	  - `showidclass`  
	  - `submitbtn`  
	  - `recall`  
- `DiscuzAjaxPreGet`
  在使用ajaxget发出请求之前触发  
  - `callback(event)`「可取消」  
    - `event` - 一个MCBBS.LoaderEvent实例  
	  - `url`  
      - `showid`  
	  - `waitid`  
	  - `loading`  
	  - `display`  
	  - `recall`  
- `DiscuzAjaxPostGet` 
  在使用ajaxget请求完成时触发  
  - `callback(event)`  
    - `event` - 一个MCBBS.LoaderEvent实例  
	  - `url`  
      - `showid`  
	  - `waitid`  
	  - `loading`  
	  - `display`  
	  - `recall`  
- `ToggleThreadPreview` 
  用户点击\[预览\]键时触发  
  - `callback(event)`「可取消」  
    - `event` - 一个MCBBS.LoaderEvent实例  
	  - `tid`  
	  - `tbody`  
- `WindowPreLoad`
  打开ajax对话窗口之前触发  
  - `callback(event)`「可取消」  
    - `event` - 一个MCBBS.LoaderEvent实例  
	  - `win`  
	  - `url`  
	  - `method`  
	  - `cache`  
	  - `menuv`  
- `MenuPreShow` 
  打开对话窗前触发，包括但不限于评分、确认窗口等  
  - `callback(event)`「可取消」  
    - `event` - 一个MCBBS.LoaderEvent实例    
	  - `detail`
- `MenuPostShow` 
  打开对话窗后触发，包括但不限于评分、确认窗口等  
  - `callback(event)`  
    - `event` - 一个MCBBS.LoaderEvent实例    
	  - `detail`  
- `MenuPreHide`  
  关闭对话窗口前触发  
  - `callback(event)`「可取消」  
    - `event` - 一个MCBBS.LoaderEvent实例  
	  - `attr`  
      - `mtype`  
- `MenuPostHide`  
  关闭对话窗口后触发  
  - `callback(event)`  
    - `event` - 一个MCBBS.LoaderEvent实例  
	  - `attr`  
      - `mtype`  