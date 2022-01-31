# chattica-planning
챗봇 관련 추상화 라이브러리, Chattica 에 대한 계획 및 기능명세 등을 작성하는 repository 입니다.

## Chattica 란?
> Discord, Slack, Kaokaotalk 등 여러 SNS 서비스의 챗봇들을 간편하게 만들 수 있게 해주는 프레임워크 입니다.

`chattica-connector` 와 `chattica-core`, `chattica-functional` 총 3가지 종류의 모듈로 이루어져 있습니다.

_프로젝트 모듈 구조도_
![](src\project-structure-diagram.png)

## Chattica Connector
> Database Connector 를 보고 생각이나서 설계한 모듈

여러 SNS 에서의 챗봇을 만들 수 있도록, 각 챗봇 API 의 내용을 추상화하여, Chattica Core 의 로직과 연동가능하게 해주는 모듈입니다.

관련 SDK 인 chattica-connector-sdk 를 구현하는 방식으로 각 SNS 별 connector 를 개발 할 수 있습니다.

sdk 에 있는 action 과 event caller 를 구현함으로서 개발 가능합니다.

## Chattica Core
> Connector 에서 받은 Event 를 Listening 해서 비즈니스 로직과 action 을 처리해주는 모듈
 
Configuration 을 통해 ConnectorBootstrap 를 받아, Connector 와 연동하여, 이벤트별로 실제 사용자의 비즈니스 로직을 수행합니다.

## Chattica Functional
> Chattica Core 를 실제 개발자가 사용하기 편하도록 Functional Programming Paradime 을 적용한 경량화 프레임워크

Flow System 과 Functional Paradime 문법을 통해 더욱 편하게 챗봇을 구성할 수 있도록 도와줍니다.

## Chattica Web
> Web 을 통해 챗봇을 더욱 편하게 구성할 수 있도록 해주는 경량화 프레임워크

챗봇 관련 action 과 event 를 http 요청으로 매핑해줍니다. 

Chattica Functional 과 같은 layer 에 속합니다.