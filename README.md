# AngularEther

---

WIP:

Instruction for getting web3 development ready with webpack5:

npm i crypto-browserify stream-browserify assert stream-http https-browserify os-browserify browser url os-browserify process -S

//polyfills.ts
import 'zone.js';

import * as process from 'process';
import { Buffer } from 'buffer';

window.process = process;
(window as any).global = window;
global.Buffer = global.Buffer || Buffer;

//tsconfig.ts 
{
  "compileOnSave": false,
  "compilerOptions": {
    "paths": {
      "crypto": ["./node_modules/crypto-browserify"],
      "stream": ["./node_modules/stream-browserify"],
      "assert": ["./node_modules/assert"],
      "http": ["./node_modules/stream-http"],
      "https": ["./node_modules/https-browserify"],
      "process": ["./node_modules/process/browser"],
      "url": ["./node_modules/url"],
      "os": ["./node_modules/os-browserify"]
    },
    "baseUrl": "./",
    ...
    // your config options / configuracion de nuestro proyecto 
  },
  "angularCompilerOptions": {
    "types" : ["node"],
    "allowSyntheticDefaultImports": true,
    "enableI18nLegacyMessageIdFormat": false,
    "strictInjectionParameters": true,
    "strictInputAccessModifiers": true,
    "noImplicitAny": false,
    "strictTemplates": true,
    "strictNullChecks": false
  }
}
