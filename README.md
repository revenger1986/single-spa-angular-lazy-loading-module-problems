# Coexisting Angular Microfrontends lazy loading problem
Single-spa lazy loading problem repro project.

#How to reproduce
1. build all subapps and host them in IIS (or something else) IN PRODUCTION MODE.
   Default urls used are: localhost:5200, 5201, 5202 and 5203.
2. Run the shell and see 'Hello i am test.component from app1', navigate to app2.
3. See console error: Uncaught (in promise): TypeError: Cannot read property 'map' of undefined

Note: If you go to app1/src/app/test/test.module and remove ReactiveFormsModule from the imports and build again. This problem doesn't occur anymore. 
But nonetheless the content of the page doesn't change to 'Hello i am test.component from app1' to 'Hello i am test.component from app2'.
This doens't only occur when using ReactiveFormsModule but it occurs when using any module.

