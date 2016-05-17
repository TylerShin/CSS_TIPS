화면 하단에 고정된 Element를 배치해야 할 때, Fixed element에 바로 아래와 같은 코드를 적용하기만 해서는 안됌. (해당 페이지 안에 input field가 있다면)

.fixed-element { position: fixed; bottom: 0; left: 0; right: 0; }

안드로이드에서 가상 키보드가 올라올 때 window size가 resize 되면서 키보드 위로 따라와버리기 때문.

이를 해결하기 위해선 input field가 focus 되었을 때, fixed-element를 hide하고 focusout(blur)되었을 때 다시 show 해주는 로직이 필요하다.

Angular Example

사용 Directive

ng-blur
ng-focus
$scope.focusInput = () => {
      angular.element('.bottom-fixed-element').hide();
    };

    $scope.blurInput = () => {
      angular.element('.bottom-fixed-element').show();
    };
};
jquery로는 focus와 focusout event를 잡아서 처리하면 된다.
