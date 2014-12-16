# 《用angularjs开发下一代Web应用》源码笔记

## 使用$rootScope.$broadcast来传递事件

reportBuilderCtrl里面广播事件：
```
$scope.addChart = function() {
            console.log('reportBuilderCtrl:addChart');
            $rootScope.$broadcast('reportBuilderCtrl.add');
        },
```
reportViewerCtrl里面接受事件并处理：
```
$scope.$on('reportBuilderCtrl.add', function(event, data) {
      return $scope.addChart();
    });

$scope.addChart = function(formId, type, fields) {
      console.log('rootScope:addChart');
      ...
    };
```

## 