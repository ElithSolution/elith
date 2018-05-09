# Elith

## Environnement Logiciel Intégré pour THérapeute

[![CircleCI](https://circleci.com/gh/ElithSolution/elith.svg?style=svg)](https://circleci.com/gh/ElithSolution/elith)

https://elements.polymer-project.org/bower_components/iron-icons/demo/index.html

## Problème avec le charset
Dans iron-ajax/iron-request.html :

  _encodeBodyObject: function(body, contentType) {
      if (typeof body == 'string') {
        return body;  // Already encoded.
      }
      var bodyObj = /** @type {Object} */ (body);
      switch(contentType) {
        case('application/json'):
          return JSON.stringify(bodyObj);
        case('application/x-www-form-urlencoded'):
          return this._wwwFormUrlEncode(bodyObj);
        // KA : AJOUT DE CETTE LIGNE POUR POUVOIR PASSER LE CHARSET
        default:
          return JSON.stringify(bodyObj);
      }
      return body;
    },