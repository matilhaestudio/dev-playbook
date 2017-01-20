#Matilha Dev Playbook

##Front End
- Do not use Jquery with angular. Use angular filters and directives instead.

##Mobile Apps
- Apps should run on angular 1.x components with Ionic
- Building process show follow this structure https://github.com/matilhaestudio/ionic-kickstart-components
- First task of app is create all views and navigation structure with transitions, look for flow errors, and test back buttons navigation
- Each view should be wrapped in ion-view tag
- Always use the Ionic hierarchy tag correctly i.e ion-nav-bar, ion-view, ion-content, ion-tab, ion-nav-view. Watch out! They're not that intuitive.
- Do not use absolute path do templates. Use template cache and ```./<template-name>.html````sintax
- Use SoC (Separation of Concerns) when using components. A component should be always able to be executed by itself with his own view and controller. Do not put components logic inside another component controller. 
- Never put logic in your controllers. i.e ```<a ng-if="$ctrl.$rootScope.controller == 'CategoryController'" [...]```
- Prefer to put show/hide elements functions at UIComponent and its controller. i.e show filter tab after search
- Keep the code DRY, do not repeat yourself. Same code must be in a function, same functions in different controllers/services/etc must be in a helper or app controller or something that makes more sense.  



