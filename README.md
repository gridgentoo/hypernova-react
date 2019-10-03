# код airbnb : : React bindings for Hypernova

Надеемся, опыт компании Airbnb пригодится всем, кто использует Node.js для решения задач серверного рендеринга.

Использование серверного рендеринга на Node.js означает повышенную вычислительную нагрузку на систему. Такая нагрузка отличается от традиционной, связанной, преимущественно, с обработкой операций ввода-вывода. Именно в таких ситуациях платформа Node.js показывает себя наилучшим образом. В нашем случае, мы, попытавшись добиться высокой производительности серверной части приложения, столкнулись с рядом проблем, которые удалось решить, поработав над архитектурой системы и воспользовавшись вспомогательными механизмами, такими, как nginx и HAProxy.

As Airbnb builds more of its Frontend around Server Side Rendering, we took a look at how to optimize our server configurations to support it.  
https://medium.com/airbnb-engineering/operationalizing-node-js-for-server-side-rendering-c5ba718acfc9  

[01.12.2014] Использование Node.js и Redis при построении приложений с высокой степенью масштабируемости https://drive.google.com/drive/folders/1l0_dWRGqlEHWwGyaJFD_0b7NTsIA7K5d  

[24 июля 2018] Node.js для решения задач серверного рендеринга в Airbnb  
https://docs.google.com/document/d/1g5DDrJBhl-9PyNFsX5NVpmAX_uX_9X1V4-SzjM6Hyvs/  

[28 марта 2019] Как мы пилили серверный рендеринг и что из этого вышло  
https://docs.google.com/document/d/1Stgohn-I9WZ6aLFiYSvsHzKZfVEiHecLgShlyjpAlew/  

[React](https://github.com/facebook/react) bindings for [Hypernova](https://github.com/airbnb/hypernova).

On the server, wraps the component in a function to render it to a HTML string given its props.

On the client, calling this function with your component scans the DOM for any server-side rendered instances of it. It then resumes those components using the server-specified props.

## Install

```sh
npm install hypernova-react
```

## Usage

Here's how to use it in your module:

```js
import { renderReact } from 'hypernova-react';
import MyComponent from './src/MyComponent.jsx';

export default renderReact(
  'MyComponent.hypernova.js', // this file's name (or really any unique name)
  MyComponent,
);
```
