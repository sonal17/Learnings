1. http://www.ivivelabs.com/blog/fix-cross-domain-ajax-request-angularjs-cors/
2. http://stackoverflow.com/questions/21154189/cross-domain-issue-in-calling-a-restful-api-using-angular-js
3.https://docs.angularjs.org/api/ng/service/$http
4.http://thibaultdenizet.com/tutorial/cors-with-angular-js-and-sinatra/
5.http://orcaman.blogspot.com/2013/07/cross-origin-http-with-angular-js.html
6.http://blog.jongallant.com/2013/08/angularjs-webapi-cors.html#.U_8VCfm2gZk
7.http://www.codeproject.com/Articles/223572/Calling-Cross-Domain-WCF-service-using-Jquery-Java
8.http://www.dotnet-tricks.com/Tutorial/wcf/X8QN260412-Calling-Cross-Domain-WCF-Service-using-Jquery.html
9.http://javidrashid.blogspot.com/2014/04/making-damn-simple-cross-domain-request.html
10.http://sharecoding.wordpress.com/tag/angularjs-cross-domain/
11.http://draptik.github.io/blog/2013/08/19/angularjs-and-cors/

** angular CORS and using $resource
https://github.com/draptik/angulardemorestful

https://github.com/tjoudeh/AngularJSAuthentication -- vgood

'use strict';
var myApp = angular.module('myApp', []); // Taking Angular Application in Javascript Variable
// Below is the code to allow cross domain request from web server through angular.js
myApp.config(['$httpProvider', function($httpProvider) {
        $httpProvider.defaults.useXDomain = true;
        delete $httpProvider.defaults.headers.common['X-Requested-With'];
    }
]);
 
