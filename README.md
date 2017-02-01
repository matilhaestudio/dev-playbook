#Matilha Dev Playbook

##Dev bootstrap
- See standard gitignore files in this repo and include on new projects
- Structure the README.md sections according our model in this repo

##Front End
- Do not use Jquery with angular. Use angular filters and directives instead.
- Do not toggle classes or remove them using document selectors or angular elements or jquery selectors like:
```document.querySelector('div.tabs').style.display = 'none';
    angular.element(document.querySelector('ion-content.has-tabs')).css('bottom', 0);
    $('body').removeClass('keyboard-open');```

##Mobile Apps
- Apps should run on angular 1.x components with Ionic
- Building process show follow this structure https://github.com/matilhaestudio/ionic-kickstart-components
- First task of app is create all views and navigation structure with transitions, look for flow errors, and test back buttons navigation
- Prefer to put show/hide elements functions at UIComponent and its controller. i.e show filter tab after search
- Always deal with promise errors, set timeouts for connections, and disable loadings when something went wrong with request


###Controller Structure
1. Main vars
2. OnInit, OnExit, OnChange functions
3. Listeners functions like $scope.$on
4. Functions that require API Calls
5. Toggle functions
6. OnClick Functions


###Ionic
- Always use the Ionic hierarchy tag correctly i.e ion-nav-bar, ion-view, ion-content, ion-tab, ion-nav-view. Watch out! They're not that intuitive.
- Each view should be wrapped in ion-view tag
- Do not use absolute path do templates. Use template cache and ```./<template-name>.html````sintax
- don't use $rootScope to set global vars. It probably will mess some state. Prefer to pass vars form one view to another using state params or using messages like $broadcast or $emit
- modules should contain run and config functions
- components should contain template and controller instances
- Prefer to use ng-if to check view for conditionals that do not need to be rendered. It avoids angular form flickering. 
- Use ng-show to elements that have active/inactive status. 
- Create listeners acording this pattern
- Never declare your controller in HTML tags like ```<div ng-controller="quizzesCtrl"></div>```

```//Listerner to toggle list from UI Manager
var deregisterListener = $rootScope.$on('on-toggle-filter', function(event, args) {
console.log("on-toggle-filter message received");
ctrl.currentActiveTab = args.tab;
ctrl.toggleFilter();
});

ctrl.$onDestroy = function() {
console.log('on destroy filter controller');
deregisterListener();
};```

- Do not refresh app 
- Do not mock back buttons

##Code best practices
- Ctrl+c and Ctrl+v whenever you want. Make sure to clean and optimize the code right after it ;) 
- Keep the code DRY, do not repeat yourself. Same code must be in a function, same functions in different controllers/services/etc must be in a helper or app controller or something that makes more sense.  
- Use SoC (Separation of Concerns) when using components. A component should be always able to be executed by itself with his own view and controller. Do not put components logic inside another component controller. 
- Avoit putting logic in your view. i.e ```<a ng-if="$ctrl.$rootScope.controller == 'CategoryController'" [...]```


##UI best practices
- Transitions between states must be as fast as possible (<1s) and loading states must be avoided except for API calls. 

##Gitflow
X.Y.Z (Major.Minor.Patch)

**Gitflow repo**: https://github.com/nvie/gitflow

**SourceTree documentation**: https://blog.sourcetreeapp.com/2012/08/01/smart-branching-with-sourcetree-and-git-flow/

###master 
O **mesmo** código que está em produção ou está pronto para ir pra produção

###dev
O **mesmo** código que está em staging ou está pronto para ir para staging

###feature-*
Código de desenvolvimento da feature antes dela estar pronta para ser testada. O primeiro commit dessa branch será **sempre** um commit para aumentar a minor version (ex: se estava na 0.1.13, o primeiro commit mudaria para 0.2.0). **Sempre** criar tag para esse commit

###hotfix-*
Branch criada **sempre** a partir da branch **master** para resolver problemas **urgentes** que apareceram em produção. Após finalizar, fazer merge com a **master e dev**, criar tag aumentando a path version **somente na master** e fazer deploy para o ambiente de produção e staging

###fix-*
Branch criada **sempre** a partir da branch **dev** para resolver problemas encontrados durante os testes de staging. Após finalizar, fazer merge com a master, criar tag aumentando a path version e fazer deploy para o ambiente de staging

## Style Guides

### Ruby: https://github.com/bbatsov/ruby-style-guide

### Rails: https://github.com/bbatsov/rails-style-guide

### AngularJS: https://github.com/johnpapa/angular-styleguide
