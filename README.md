#Matilha Dev Playbook

##Front End
- Do not use Jquery with angular. Use angular filters and directives instead.

##Mobile Apps
- Apps should run on angular 1.x components with Ionic
- Building process show follow this structure https://github.com/matilhaestudio/ionic-kickstart-components
- First task of app is create all views and navigation structure with transitions, look for flow errors, and test back buttons navigation
- Each view should be wrapped in ion-view tag
- Use SoC (Separation of Concerns) when using components. A component should be always able to be executed by itself with his own view and controller. Do not put components logic inside another component controller. 
