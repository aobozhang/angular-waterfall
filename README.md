# angular-waterfall
a responsive waterfall plugin of angular<br>
定列自适应瀑布流指令

# install
```
bower install git+https://github.com/aobozhang/angular-waterfall.git --save
```

# options
* contentWidth(optional) 外层容器宽度，不设则auto
    * 95%
    * 360px
    * ...
* cols(optional) 指定显示列数，默认6

```
<ul class="waterfall-list" ng-waterfall cols="2" contentWidth="7.34rem">
    <li></li>
    ...
</ul>
```
# example
1.模块注入
```javascript
    angular.module('angularWaterfallApp',["ngWaterfall"])
```

2.模板

```html
<div ng-waterfall-container style="height:100%">
    <div class="water-fall container">
        <ul class="waterfall-list" ng-waterfall cols="6">
            <li ng-repeat="image in images" repeat-finished>
                <div class="data-block">
                    <img src="{{image.url}}" alt="{{image.summary}}"/>
                    <p>{{image.title}}</p>
                    <p>{{image.summary}}</p>
                </div>
            </li>
            <div class="loadMore" ng-if="loadMore" ng-infinite-scroll ng-click="loadMoreData()">{{text}}</div>
        </ul>
    </div>
</div>
```

3.controller

```javascript
    page++;
    $scope.$on("waterfall:loadMore",function(){//滚动自动填充事件
            $scope.loadMoreData();
    })

```
