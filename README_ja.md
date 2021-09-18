# Modular Monolith with DDD

Full Modular Monolith .NET application with Domain-Driven Design approach.

## CI

![](https://github.com/kgrzybek/modular-monolith-with-ddd/workflows/Build%20Pipeline/badge.svg)

## FrontEnd application

FrontEnd application : [Modular Monolith With DDD: FrontEnd React application](https://github.com/kgrzybek/modular-monolith-with-ddd-fe-react)

## Table of contents

[1. Introduction](#1-Introduction)
[1.はじめに](#1-はじめに)

&nbsp;&nbsp;[1.1 Purpose of this Repository](#11-purpose-of-this-repository)
&nbsp;&nbsp;[1.1 このリポジトリの目的](#11-purpos-of-this-repository)

&nbsp;&nbsp;[1.2 Out of Scope](#12-out-of-scope)
&nbsp;&nbsp;[1.2 範囲外](#12-範囲外)

&nbsp;&nbsp;[1.3 Reason](#13-reason)
&nbsp;&nbsp;[1.3 理由](#13-reason)

&nbsp;&nbsp;[1.4 Disclaimer](#14-disclaimer)
&nbsp;&nbsp;[1.4 免責事項](#14-disclaimer)

&nbsp;&nbsp;[1.5 Give a Star](#15-give-a-star)
&nbsp;&nbsp;[1.5 星をあげる](#15-星をあげる)

&nbsp;&nbsp;[1.6 Share It](#16-share-it)
&nbsp;&nbsp;[1.6 シェアする](#16-シェアする)

[2. Domain](#2-Domain)
[2.ドメイン](#2-Domain)

&nbsp;&nbsp;[2.1 Description](#21-description)
&nbsp;&nbsp;[2.1 ディスクリプション](#21-description)

&nbsp;&nbsp;[2.2 Conceptual Model](#22-conceptual-model)
&nbsp;&nbsp;[2.2 概念モデル](#22-conceptual-model)

&nbsp;&nbsp;[2.3 Event Storming](#23-event-storming)
&nbsp;&nbsp;[2.3 イベントストーミング](#23-event-storming)

[3. Architecture](#3-Architecture)
[3.アーキテクチャー](#3-アーキテクチャー)

&nbsp;&nbsp;[3.0 C4 Model](#30-c4-model)
&nbsp;&nbsp;[3.0 C4 モデル](#30-C4-モデル)

&nbsp;&nbsp;[3.1 High Level View](#31-high-level-view)
&nbsp;&nbsp;[3.1 ハイレベルビュー](#31-ハイレベル-ビュー)

&nbsp;&nbsp;[3.2 Module Level View](#32-module-level-view)
&nbsp;&nbsp;[3.2 モジュール・レベル・ビュー](#32-モジュール・レベル・ビュー)

&nbsp;&nbsp;[3.3 API and Module Communication](#33-api-and-module-communication)
&nbsp;&nbsp;[3.3 API とモジュールの通信](#33-api-and-module-communication)

&nbsp;&nbsp;[3.4 Module Requests Processing via CQRS](#34-module-requests-processing-via-cqrs)
&nbsp;&nbsp;[3.4 CQRS によるモジュール要求の処理](#34-module-requests-processing-via-cqrs)

&nbsp;&nbsp;[3.5 Domain Model Principles and Attributes](#35-domain-model-principles-and-attributes)
&nbsp;&nbsp;[3.5 ドメインモデルの原則と属性](#35-domain-model-principles-and-attributes)

&nbsp;&nbsp;[3.6 Cross-Cutting Concerns](#36-cross-cutting-concerns)
&nbsp;&nbsp;[3.6 クロスカッティング・コンサーン](#36-cross-cutting-concerns)

&nbsp;&nbsp;[3.7 Modules Integration](#37-modules-integration)
&nbsp;&nbsp;[3.7 モジュール統合](#37-modules-integration)

&nbsp;&nbsp;[3.8 Internal Processing](#38-internal-processing)
&nbsp;&nbsp;[3.8 内部処理](#38-内部処理)

&nbsp;&nbsp;[3.9 Security](#39-security)
&nbsp;&nbsp;[3.9 セキュリティ](#39-セキュリティ)

&nbsp;&nbsp;[3.10 Unit Tests](#310-unit-tests)
&nbsp;&nbsp;[3.10 ユニットテスト](#310-unit-tests)

&nbsp;&nbsp;[3.11 Architecture Decision Log](#311-architecture-decision-log)
&nbsp;&nbsp;[3.11 アーキテクチャ決定ログ](#311-architecture-decision-log)

&nbsp;&nbsp;[3.12 Architecture Unit Tests](#312-architecture-unit-tests)
&nbsp;&nbsp;[3.12 アーキテクチャーのユニットテスト](#312-アーキテクチャーのユニットテスト)

&nbsp;&nbsp;[3.13 Integration Tests](#313-integration-tests)
&nbsp;&nbsp;[3.13 統合テスト](#313-integration-tests)

&nbsp;&nbsp;[3.14 System Integration Testing](#314-system-integration-testing)
&nbsp;&nbsp;[3.14 システム統合テスト](#314-system-integration-testing)

&nbsp;&nbsp;[3.15 Event Sourcing](#315-event-sourcing)
&nbsp;&nbsp;[3.15 イベントソーシング](#315-event-sourcing)

&nbsp;&nbsp;[3.16 Database change management](#316-database-change-management)
&nbsp;&nbsp;[3.16 データベース変更管理](#316-database-change-management)

&nbsp;&nbsp;[3.17 Continuous Integration](#317-continuous-integration)
&nbsp;&nbsp;[3.17 継続的インテグレーション](#317-継続的インテグレーション)

&nbsp;&nbsp;[3.18 Static code analysis](#318-static-code-analysis)
&nbsp;&nbsp;[3.18 スタティックコード解析](#318-static-code-analysis)

[4. Technology](#4-technology)
[技術](#4-技術)

[5. How to Run](#5-how-to-run)
[5.走り方](#5-how-to-run)

[6. Contribution](#6-contribution)
[6.貢献](#6-貢献)

[7. Roadmap](#7-roadmap)
[7.ロードマップ](#7-roadmap)

[8. Authors](#8-authors)
[8.オーサーズ](#8-authors)

[9. License](#9-license)
[9.ライセンス](#9-license)

[10. Inspirations and Recommendations](#10-inspirations-and-recommendations)
[10.ひらめきと提言](#10-inspirations-and-recommendations)

## 1. Introduction

### 1.1 Purpose of this Repository

This is a list of the main goals of this repository:

- Showing how you can implement a **monolith** application in a **modular** way
- Presentation of the **full implementation** of an application
  - This is not another simple application
  - This is not another proof of concept (PoC)
  - The goal is to present the implementation of an application that would be ready to run in production
- Showing the application of **best practices** and **object-oriented programming principles**
- Presentation of the use of **design patterns**. When, how and why they can be used
- Presentation of some **architectural** considerations, decisions, approaches
- Presentation of the implementation using **Domain-Driven Design** approach (**tactical** patterns)
- Presentation of the implementation of **Unit Tests** for Domain Model (Testable Design in mind)
- Presentation of the implementation of **Integration Tests**
- Presentation of the implementation of **Event Sourcing**
- Presentation of **C4 Model**
- Presentation of **diagram as text** approach

### 1.1 このリポジトリの目的

このリポジトリの主な目的を列挙します。

- monolith**アプリケーションを**modular\*\*な方法で実装する方法の紹介
- アプリケーションの**完全な実装**の提示
  - これは単純なアプリケーションではありません。
  - 概念実証(PoC)ではありません。
  - 本番環境ですぐに実行できるアプリケーションの実装を提示することが目的です。
- ベストプラクティスとオブジェクト指向プログラミングの原則の適用を示すこと
- デザインパターン\*\*の使用方法の説明。いつ、どのように、なぜ使用するのか
- アーキテクチャーに関する検討事項、決定事項、アプローチを説明します。
- ドメイン駆動設計**のアプローチ（**戦術\*\*パターン）を用いた実装の紹介
- ドメインモデルに対する**ユニットテスト**の実装についての発表（テスト可能な設計を念頭においています
- 統合テスト\*\*の実装方法の紹介
- イベントソーシングの実装方法の紹介
- C4 モデル\*\*の発表
- テキストとしてのダイアグラムの提示\*\*アプローチ

### 1.2 Out of Scope

This is a list of subjects which are out of scope for this repository:

- Business requirements gathering and analysis
- System analysis
- Domain exploration
- Domain distillation
- Domain-Driven Design **strategic** patterns
- Architecture evaluation, quality attributes analysis
- Integration, system tests
- Project management
- Infrastructure
- Containerization
- Software engineering process
- Deployment process
- Maintenance
- Documentation

### 1.2 対象外

1.2 対象外 本リポジトリで対象外とするテーマを以下に示します。

- ビジネス要求の収集と分析
- システム分析
- ドメイン探査
- ドメインディスティレーション
- ドメイン駆動設計 **戦略的** パターン
- アーキテクチャ評価、品質属性分析
- 統合、システムテスト
- プロジェクト管理
- インフラ
- コンテナ化
- ソフトウェアエンジニアリングプロセス
- デプロイメントプロセス
- メンテナンス
- ドキュメント作成

### 1.3 Reason

The reason for creating this repository is the lack of something similar. Most sample applications on GitHub have at least one of the following issues:

- Very, very simple - few entities and use cases implemented
- Not finished (for example there is no authentication, logging, etc..)
- Poorly designed (in my opinion)
- Poorly implemented (in my opinion)
- Not well described
- Assumptions and decisions are not clearly explained
- Implements "Orders" domain - yes, everyone knows this domain, but something different is needed
- Implemented in old technology
- Not maintained

To sum up, there are some very good examples, but there are far too few of them. This repository has the task of filling this gap at some level.

### 1.3 理由

このリポジトリを作成した理由は、似たようなものがないからです。GitHub で公開されているサンプルアプリケーションの多くは、以下のような問題を少なくとも 1 つは抱えています。

- 非常にシンプルで、実装されているエンティティやユースケースが少ない。
- 完成されていない（例えば、認証やロギングなどが行われていない）。
- 設計が悪い（私見
- 実装が不十分である（私見
- よく説明されていない
- 前提条件や決定事項が明確に説明されていない
- 注文」ドメインを実装している - 確かにこのドメインは誰もが知っているが、何か違うものが必要である。
- 古い技術で実装されている
- メンテナンスされていない

要約すると、非常に優れた例はありますが、その数はあまりにも少ないのです。このリポジトリは、このギャップをあるレベルで埋めるという課題を持っています。

### 1.4 Disclaimer

Software architecture should always be created to resolve specific **business problems**. Software architecture always supports some quality attributes and at the same time does not support others. A lot of other factors influence your software architecture - your team, opinions, preferences, experiences, technical constraints, time, budget, etc.

Always functional requirements, quality attributes, technical constraints and other factors should be considered before an architectural decision is made.

Because of the above, the architecture and implementation presented in this repository is **one of the many ways** to solve some problems. Take from this repository as much as you want, use it as you like but remember to **always pick the best solution which is appropriate to the problem class you have**.

### 1.4 免責事項

ソフトウェア・アーキテクチャは、常に特定の**ビジネス上の問題**を解決するために作成されるべきである。ソフトウェアアーキテクチャは、常にある品質属性をサポートし、同時に他の品質属性をサポートしません。ソフトウェアアーキテクチャには、チーム、意見、好み、経験、技術的制約、時間、予算など、その他多くの要因が影響します。

アーキテクチャを決定する前に、常に機能要件、品質属性、技術的制約、その他の要因を考慮する必要があります。

以上のことから、このリポジトリで紹介されているアーキテクチャや実装は、いくつかの問題を解決するための**多くの方法**のうちの 1 つです。このリポジトリから好きなだけ、好きなように利用してください。ただし、**常に、自分が抱えている問題クラスに適した最良の解決策を選ぶ**ことを忘れないでください。

### 1.5 Give a Star

My primary focus in this project is on quality. Creating a good quality product involves a lot of analysis, research and work. It takes a lot of time. If you like this project, learned something or you are using it in your applications, please give it a star :star:. This is the best motivation for me to continue this work. Thanks!

### 1.5 星をつける

このプロジェクトで私が最も重視しているのは、品質です。良い品質の製品を作るには、多くの分析、研究、作業が必要です。多くの時間を要します。このプロジェクトを気に入ってくださったり、何かを学んでくださったり、自分のアプリケーションで使ってくださったりした場合は、ぜひ星 :star: をつけてください。 これが、私がこの仕事を続けるための最高のモチベーションとなります。ありがとうございました。

### 1.6 Share It

There are very few really good examples of this type of application. If you think this repository makes a difference and is worth it, please share it with your friends and on social networks. I will be extremely grateful.

### 1.6 Share It

この種のアプリケーションで本当に良い例はほとんどありません。もし、このリポジトリが変化をもたらし、価値があると思われるなら、友人やソーシャルネットワークでシェアしてください。大変ありがたく思います。

## 2. Domain

## 2. ドメイン

### 2.1 Description

### 2.1 説明

**Definition:**

> Domain - A sphere of knowledge, influence, or activity. The subject area to which the user applies a program is the domain of the software. [Domain-Driven Design Reference](http://domainlanguage.com/ddd/reference/), Eric Evans

The **Meeting Groups** domain was selected for the purposes of this project based on the [Meetup.com](https://www.meetup.com/) system.

> ドメイン - 知識、影響力、または活動の範囲のこと。ユーザーがプログラムを適用する対象領域がソフトウェアのドメインである。[Domain-Driven Design Reference](http://domainlanguage.com/ddd/reference/), Eric Evans

このプロジェクトの目的のために、[Meetup.com](https://www.meetup.com/)のシステムに基づいて**Meeting Groups**ドメインが選択されました。

**Main reasons for selecting this domain:**

\*\*このドメインを選択した主な理由は次の通りです。

- It is common, a lot of people use the Meetup site to organize or attend meetings
- There is a system for it, so everyone can check this implementation against a working site which supports this domain
- It is not complex so it is easy to understand
- It is not trivial - there are some business rules and logic and it is not just CRUD operations
- You don't need much specific domain knowledge unlike other domains like financing, banking, medical
- It is not big so it is easier to implement

- 多くの人が Meetup サイトを使ってミーティングを開催したり、参加したりしている。
- このドメインをサポートするシステムがあるので、誰もがこの実装を、このドメインをサポートする現役のサイトに照らし合わせることができる。
- 複雑ではないので、理解しやすい。
- 単なる CRUD 操作ではなく、いくつかのビジネスルールやロジックがあります。
- 金融、銀行、医療などの他のドメインとは異なり、特定のドメインの知識はあまり必要ありません。
- 大規模ではないので、実装が容易です。

**Meetings**

\*\*ミーティング

The main business entities are `Member`, `Meeting Group` and `Meeting`. A `Member` can create a `Meeting Group`, be part of a `Meeting Group` or can attend a `Meeting`.

A `Meeting Group Member` can be an `Organizer` of this group or a normal `Member`.

Only an `Organizer` of a `Meeting Group` can create a new `Meeting`.

A `Meeting` has attendees, not attendees (`Members` which declare they will not attend the `Meeting`) and `Members` on the `Waitlist`.

A `Meeting` can have an attendee limit. If the limit is reached, `Members` can only sign up to the `Waitlist`.

A `Meeting Attendee` can bring guests to the `Meeting`. The number of guests allowed is an attribute of the `Meeting`. Bringing guests can be unallowed.

A `Meeting Attendee` can have one of two roles: `Attendee` or `Host`. A `Meeting` must have at least one `Host`. The `Host` is a special role which grants permission to edit `Meeting` information or change the attendees list.

A `Member` can comment `Meetings`. A `Member` can reply to, like other `Comments`. `Organizer` manages commenting of `Meeting` by `Meeting Commenting Configuration`. `Organizer` can delete any `Comment`.

Each `Meeting Group` must have an organizer with active `Subscription`. One organizer can cover 3 `Meeting Groups` by his `Subscription`.

Additionally, Meeting organizer can set an `Event Fee`. Each `Meeting Attendee` is obliged to pay the fee. All guests should be paid by `Meeting Attendee` too.

主なビジネスエンティティは `Member`, `Meeting Group`, `Meeting` です。メンバー`は`ミーティンググループ`を作成したり、`ミーティンググループ`のメンバーになったり、`ミーティング`に参加したりすることができる。

ミーティンググループのメンバー "はこのグループの "オーガナイザー "になることもできるし、通常の "メンバー "になることもできる。

ミーティンググループ`の`オーガナイザー`だけが新しい`ミーティング`を作成することができる。

ミーティング`には参加者、不参加者（`ミーティング`に参加しないことを宣言した`メンバー`）、`ウェイティングリスト`に登録された`メンバー`がいる。

ミーティング`には参加者の上限を設定することができる。定員に達した場合、`メンバー`は`ウェイティングリスト`にのみ登録することができる。

ミーティングの参加者`はゲストを連れてくることができます。許可されるゲストの数は `Meeting` の属性である。ゲストの同伴は許可されないこともあります。

ミーティングの参加者`は`参加者`と`ホスト`の2つの役割のうちの1つを持つことができます。ミーティング`には少なくとも 1 つの`ホスト`が必要です。ホスト`は特別なロールで、`ミーティング`の情報を編集したり、出席者のリストを変更する権限を与えられます。

メンバー`は`ミーティング`にコメントすることができます。メンバー」は他の「コメント」と同様に返信することができます。オーガナイザ`は `Meeting Commenting Configuration` によって `Meeting` のコメントを管理する。オーガナイザー」は「コメント」を削除することができる。

各 `Meeting Group` には有効な `Subscription` を持つオーガナイザーが必要である。1 人の主催者は 3 つの「ミーティンググループ」を自分の「サブスクリプション」でカバーすることができます。

さらに、ミーティングの主催者は「イベント料金」を設定することができる。各「ミーティングの参加者」はその料金を支払う義務がある。すべてのゲストも `Meeting Attendee` が支払う必要があります。

**Administration**

**管理**について

To create a new `Meeting Group`, a `Member` needs to propose the group. A `Meeting Group Proposal` is sent to `Administrators`. An `Administrator` can accept or reject a `Meeting Group Proposal`. If a `Meeting Group Proposal` is accepted, a `Meeting Group` is created.

新しい `Meeting Group` を作成するには、`Member` がグループを提案する必要がある。ミーティンググループの提案 "は "管理者 "に送られます。管理者 "は "ミーティンググループの提案 "を承認するか拒否することができる。ミーティンググループの提案 "が受け入れられた場合、"ミーティンググループ "が作成される。

**Payments**

**支払い**について

Each `Member` who is the `Payer` can buy the `Subscription`. He needs to pay the `Subscription Payment`. `Subscription` can expire so `Subscription Renewal` is required (by `Subscription Renewal Payment` payment to keep `Subscription` active).

When the `Meeting` fee is required, the `Payer` needs to pay `Meeting Fee` (through `Meeting Fee Payment`).

支払い者である各 `メンバー` は `購読' を購入することができる。メンバーは「購読料」を支払う必要があります。購読権」は期限切れになることがあるので、「購読権の更新」が必要になる（「購読権の更新料」を支払うことで「購読権」を有効に保つことができる）。

**Users**

**ユーザー**.

Each `Administrator`, `Member` and `Payer` is a `User`. To be a `User`, `User Registration` is required and confirmed.

Each `User` is assigned one or more `User Role`.

Each `User Role` has set of `Permissions`. A `Permission` defines whether `User` can invoke a particular action.

管理者"、"メンバー"、"支払者 "はそれぞれ "ユーザ "となる。ユーザー "になるためには、`ユーザー登録`が必要であり、確認されなければならない。

各`ユーザ`には一つ以上の`ユーザロール`が割り当てられる。

各「ユーザロール」は一連の「パーミッション」を持つ。パーミッション "は、`ユーザ`が特定のアクションを実行できるかどうかを定義する。

### 2.2 Conceptual Model

### 2.2 概念モデル

**Definition:**

> Conceptual Model - A conceptual model is a representation of a system, made of the composition of concepts that are used to help people know, understand, or simulate a subject the model represents. [Wikipedia - Conceptual model](https://en.wikipedia.org/wiki/Conceptual_model)

> 概念モデル - 概念モデルとは、モデルが表現する対象を人々が知り、理解し、シミュレートするために使用される概念の構成からなる、システムの表現である。[Wikipedia - Conceptual model](https://en.wikipedia.org/wiki/Conceptual_model)

**Conceptual Model**

PlantUML version:
![](https://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/kgrzybek/modular-monolith-with-ddd/master/docs/PlantUML/Conceptual_Model.puml)

VisualParadigm version (not maintained, only for demonstration):
![](docs/Images/Conceptual_Model.png)

**Conceptual Model of commenting feature**
![](https://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/kgrzybek/modular-monolith-with-ddd/master/docs/PlantUML/Commenting_Conceptual_Model.puml)

### 2.3 Event Storming

### 2.3 イベントストーミング

While a Conceptual Model focuses on structures and relationships between them, **behavior** and **events** that occur in our domain are more important.

There are many ways to show behavior and events. One of them is a light technique called [Event Storming](https://www.eventstorming.com/) which is becoming more popular. Below are presented 3 main business processes using this technique: user registration, meeting group creation and meeting organization.

Note: Event Storming is a light, live workshop. One of the possible outputs of this workshop is presented here. Even if you are not doing Event Storming workshops, this type of process presentation can be very valuable to you and your stakeholders.

概念モデルでは、構造や構造間の関係を重視しますが、ドメイン内で発生する**behavior**や**events**はより重要です。

振る舞いやイベントを示す方法はたくさんあります。その一つが[Event Storming](https://www.eventstorming.com/)と呼ばれる軽快な手法で、最近人気が高まっています。以下では、このテクニックを使った 3 つの主要なビジネスプロセスを紹介します：ユーザー登録、会議グループの作成、会議の開催です。

注：Event Storming は、ライトなライブワークショップです。このワークショップで考えられるアウトプットの一つをここで紹介します。Event Storming のワークショップを行っていなくても、このようなプロセスのプレゼンテーションは、あなたやあなたのステークホルダーにとって非常に価値のあるものになるでしょう。

**User Registration process**

**ユーザー登録プロセス**について

---

![](docs/Images/User_Registration.jpg)

---

**Meeting Group creation**
![](docs/Images/Meeting_Group_Creation.jpg)

---

**Meeting organization**
![](docs/Images/Meeting_Organization.jpg)

---

**Payments**
![](docs/Images/Payments_EventStorming_Design.jpg)
[Download high resolution file](docs/Images/Payments_EventStorming_Design_HighRes.jpg)

---

## 3. Architecture

### 3.0 C4 Model

[C4 model](https://c4model.com/) is a lean graphical notation technique for modelling the architecture of software systems. <br>

As can be found on the website of the author of this model ([Simon Brown](https://simonbrown.je/)): _The C4 model was created as a way to help software development teams describe and communicate software architecture, both during up-front design sessions and when retrospectively documenting an existing codebase_ <br>

_Model C4_ defines 4 levels (views) of the system architecture: _System Context_, _Container_, _Component_ and _Code_. Below are examples of each of these levels that describe the architecture of this system. <br>

_Note: The [PlantUML](https://plantuml.com/) (diagram as text) component was used to describe all C4 model levels. Additionally, for levels C1-C3, a [C4-PlantUML](https://github.com/plantuml-stdlib/C4-PlantUML) plug-in connecting PlantUML with the C4 model was used_.

[C4 モデル](https://c4model.com/)は、ソフトウェアシステムのアーキテクチャをモデル化するための、無駄のないグラフィカルな表記法です。<br>。

このモデルの作者である[Simon Brown](https://simonbrown.je/)のホームページにも記載されています。\*C4 モデルは、ソフトウェア開発チームがソフトウェア・アーキテクチャを記述し、コミュニケーションするのに役立つ方法として作成されました。

*C4 モデルでは、システムアーキテクチャの 4 つのレベル（ビュー）を定義しています。<br> *モデル C4*では、システムアーキテクチャの 4 つのレベル（ビュー）を定義しています：*System Context*, *Container*, *Component*, *Code\*。以下は、このシステムのアーキテクチャを説明する、これらの各レベルの例です。<br>

_注：C4 モデルの全てのレベルを記述するために、[PlantUML](https://plantuml.com/) (diagram as text) コンポーネントが使用されました。また、C1 ～ C3 のレベルには、PlantUML と C4 モデルを接続するプラグインである[C4-PlantUML](https://github.com/plantuml-stdlib/C4-PlantUML)を使用しています_。

#### 3.0.1 C1 System Context

![](http://www.plantuml.com/plantuml/png/7OrDgeD048JtxnGl1z0ca5LMGWuYutIZulIqz0_6d3vZDbLG5Dytc2VruF9tMsikWHHQ_XVttPu0cev-Nds9AOmqItMgtcTXs6Rzd1Djm89HadOiLKgxTiSLY0YSp4a19Hky7f3levrjuV77UNk_Nzg1AhR-0W00)

#### 3.0.2 C2 Container

![](http://www.plantuml.com/plantuml/png/5OrDgiCm30RtxnIl1uW5fQkk0Zr8SIoHcDXIq0-XFNtZpVTjXfdPFAj7Rt-togK5KcZxtzmFUm9eFjDQVOibZBG8Ex6d8XtsLR-VXNReWj6oJbrOseLEvnX4X9xDIG6b6BmUKExl8SYLITCnYZCnNly3)

#### 3.0.3 C3 Component (high-level)

![](http://www.plantuml.com/plantuml/png/5OqxZiCm30NxFSNc01QBf4fb80S9P96m3Kkam0-CvFIHc_UQ6SnidjMZrR_RpgK6KcZztzoxFG4qdsdTVOibZBG8Ex6d8WsELR-VXGveWb6pJarOwa2dynf4X9RDIG6b6BmUKExl8NPXOhVKh-HCZED_)

#### 3.0.4 C3 Component (module-level)

![](http://www.plantuml.com/plantuml/png/7OqzheCm48JxTugN0y0MIPKAAGT1nhi2XBrhxOzGSlgOD3FDVFDDvaazQlcxxPnB88MM_yszsHD0qpckks-nX95cOIVsCKk5OzNFUw43gc2Kf4CLbjAdmta58a9DvgI0aWrU3yZtkODDk5_O_CDeR9Tv8iRUNm00)

#### 3.0.5 C4 Code (meeting group aggregate)

![](http://www.plantuml.com/plantuml/png/5OqxheD0303xTugN0x1kg58XvI3HObk0yAwHFqB9wGFDJ3FIJ1xL8flyFRQEaiHfyhz67Fu4i7gMPOirvtGsr1xSew0ss1VxVcRUeIcbL1kQTfKh7SuRH0IjUh01AJgyHi3nZLBTot7V9kvq-GS0)

### 3.1 High Level View

![](docs/Images/Architecture_high_level.png)

**Module descriptions:**

**モジュールの説明：**。

- **API** - Very thin ASP.NET MVC Core REST API application. Main responsibilities are:
  1. Accept request
  2. Authenticate and authorize request (using User Access module)
  3. Delegate work to specific module sending Command or Query
  4. Return response
- **User Access** - responsible for user authentication, authorization and registration
- **Meetings** - implements Meetings Bounded Context: creating meeting groups, meetings
- **Administration** - implements Administration Bounded Context: implements administrative tasks like meeting group proposal verification
- **Payments** - implements Payments Bounded Context: implements all functionalities associated with payments
- **In Memory Events Bus** - Publish/Subscribe implementation to asynchronously integrate all modules using events ([Event Driven Architecture](https://en.wikipedia.org/wiki/Event-driven_architecture)).

- API\*\* - 非常に薄い ASP.NET MVC Core REST API アプリケーションです。主な責務は以下の通りです。
  1. リクエストの受付
  2. (User Access モジュールを使用して)リクエストを認証し、承認する
  3. コマンドまたはクエリを送信して、特定のモジュールに作業を委ねる
  4. 応答を返す
- User Access\*\* - ユーザーの認証、承認、登録を行う。
- **Meetings** - Meetings Bounded Context の実装：ミーティンググループやミーティングの作成を行います。
- Administration\*\* - Administration Bounded Context の実装：ミーティンググループの提案の確認などの管理タスクを実装する。
- Payments\*\* - Payments Bounded Context の実装：支払いに関連するすべての機能を実装しています。
- **In Memory Events Bus** - イベントを使用してすべてのモジュールを非同期的に統合するための Publish/Subscribe 実装（[Event Driven Architecture](https://en.wikipedia.org/wiki/Event-driven_architecture)）。

**Key assumptions:**

**主な前提条件：\***。

1. API contains no application logic
2. API communicates with Modules using a small interface to send Queries and Commands
3. Each Module has its own interface which is used by API
4. **Modules communicate each other only asynchronously using Events Bus** - direct method calls are not allowed
5. Each Module **has it's own data** in a separate schema - shared data is not allowed
   - Module data could be moved into separate databases if desired
6. Modules can only have a dependency on the integration events assembly of other Module (see [Module level view](#32-module-level-view))
7. Each Module has its own [Composition Root](https://freecontent.manning.com/dependency-injection-in-net-2nd-edition-understanding-the-composition-root/), which implies that each Module has its own Inversion-of-Control container
8. API as a host needs to initialize each module and each module has an initialization method
9. Each Module is **highly encapsulated** - only required types and members are public, the rest are internal or private

10. API はアプリケーションロジックを含まない
11. API はモジュールと通信し、クエリーとコマンドを送信するための小さなインターフェースを使用します。
12. 各モジュールは、API で使用される独自のインターフェースを持っています。
13. **モジュールはイベントバスを使用して非同期的にのみ相互に通信します** - 直接的なメソッドコールはできません。
14. 5. 各モジュールは**独自のデータ**を個別のスキーマに持っている - データの共有はできない。
    - モジュールのデータは、必要に応じて別のデータベースに移すことができる
15. 6. モジュールは、他のモジュールの統合イベントアセンブリにのみ依存することができます ([モジュールレベルの表示](#32-module-level-view)を参照)。
16. 各モジュールは独自の[Composition Root](https://freecontent.manning.com/dependency-injection-in-net-2nd-edition-understanding-the-composition-root/)を持ち、これは各モジュールが独自の Inversion-of-Control コンテナを持つことを意味します。
17. ホストである API は各モジュールを初期化する必要があり、各モジュールは初期化メソッドを持っている。
18. 各モジュールは **高度にカプセル化されている** - 必要な型とメンバーのみが公開され、残りは内部またはプライベートである。

### 3.2 Module Level View

![](docs/Images/Module_level_diagram.png)

Each Module has [Clean Architecture](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html) and consists of the following submodules (assemblies):

- **Application** - the application logic submodule which is responsible for requests processing: use cases, domain events, integration events, internal commands.
- **Domain** - Domain Model in Domain-Driven Design terms implements the applicable [Bounded Context](https://martinfowler.com/bliki/BoundedContext.html)
- **Infrastructure** - infrastructural code responsible for module initialization, background processing, data access, communication with Events Bus and other external components or systems
- **IntegrationEvents** - **Contracts** published to the Events Bus; only this assembly can be called by other modules

各モジュールは[Clean Architecture](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)で、以下のサブモジュール(アセンブリ)で構成されています。

- **Application** - アプリケーションロジックサブモジュールで、ユースケース、ドメインイベント、統合イベント、内部コマンドなどのリクエスト処理を担当します。
- **Domain** - ドメイン駆動設計用語でのドメインモデルで、該当する[Bounded Context](https://martinfowler.com/bliki/BoundedContext.html)を実装します。
- **インフラストラクチャ** - モジュールの初期化、バックグラウンド処理、データアクセス、イベントバスや他の外部コンポーネントやシステムとの通信を担当するインフラストラクチャコードです。
- **IntegrationEvents** - イベントバスに発行された**契約**で、このアセンブリのみが他のモジュールから呼び出すことができます。

![](docs/Images/VSSolution.png)

**Note:** Application, Domain and Infrastructure assemblies could be merged into one assembly. Some people like horizontal layering or more decomposition, some don't. Implementing the Domain Model or Infrastructure in separate assembly allows encapsulation using the [`internal`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/internal) keyword. Sometimes Bounded Context logic is not worth it because it is too simple. As always, be pragmatic and take whatever approach you like.

**注：**アプリケーション、ドメイン、インフラストラクチャの各アセンブリは、1 つのアセンブリに統合することができます。水平方向の重ね合わせや分解を好む人もいれば、そうでない人もいます。ドメインモデルやインフラストラクチャを別のアセンブリに実装することで、[`internal`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/internal)キーワードを使ったカプセル化が可能になります。Bounded Context のロジックがシンプルすぎて価値がない場合もあります。いつものように、現実的に考えて、好きなアプローチを取ってください。

### 3.3 API and Module Communication

### 3.3 API とモジュールの通信

The API only communicates with Modules in two ways: during module initialization and request processing.

**Module initialization**

Each module has a static `Initialize` method which is invoked in the API `Startup` class. All configuration needed by this module should be provided as arguments to this method. All services are configured during initialization and the Composition Root is created using the Inversion-of-Control Container.

API がモジュールと通信するのは、モジュールの初期化時とリクエスト処理時の 2 通りです。

\*\*モジュールの初期化

各モジュールは静的な`Initialize`メソッドを持ち、これは API の`Startup`クラスで呼び出されます。このモジュールが必要とするすべての設定は、このメソッドの引数として提供されなければなりません。初期化時にはすべてのサービスが設定され、Inversion-of-Control コンテナを使ってコンポジションルートが作成されます。

```csharp
public static void Initialize(
    string connectionString,
    IExecutionContextAccessor executionContextAccessor,
    ILogger logger,
    EmailsConfiguration emailsConfiguration)
{
    var moduleLogger = logger.ForContext("Module", "Meetings");

    ConfigureCompositionRoot(connectionString, executionContextAccessor, moduleLogger, emailsConfiguration);

    QuartzStartup.Initialize(moduleLogger);

    EventsBusStartup.Initialize(moduleLogger);
}
```

**Request processing**

**リクエスト処理**について

Each module has the same interface signature exposed to the API. It contains 3 methods: command with result, command without result and query.

各モジュールは、API に公開されている同じインターフェース・シグネチャーを持っています。結果付きコマンド、結果なしコマンド、クエリの 3 つのメソッドがあります。

```csharp
public interface IMeetingsModule
{
    Task<TResult> ExecuteCommandAsync<TResult>(ICommand<TResult> command);

    Task ExecuteCommandAsync(ICommand command);

    Task<TResult> ExecuteQueryAsync<TResult>(IQuery<TResult> query);
}
```

**Note:** Some people say that processing a command should not return a result. This is an understandable approach but sometimes impractical, especially when you want to immediately return the ID of a newly created resource. Sometimes the boundary between Command and Query is blurry. One example is `AuthenticateCommand` - it returns a token but it is not a query because it has a side effect.

**Note:** 「コマンドを処理しても結果を返すべきではない」という意見があります。これは理解できるアプローチではありますが、特に新しく作成されたリソースの ID をすぐに返したい場合など、実用的でないこともあります。コマンドとクエリの境界が曖昧な場合があります。例えば、`AuthenticateCommand` はトークンを返しますが、副作用があるのでクエリではありません。

### 3.4 Module Requests Processing via CQRS

### 3.4 CQRS によるモジュール要求の処理

Processing of Commands and Queries is separated by applying the architectural style/pattern [Command Query Responsibility Segregation (CQRS)](https://docs.microsoft.com/en-us/azure/architecture/patterns/cqrs).

コマンドとクエリの処理は、アーキテクチャスタイル/パターン[Command Query Responsibility Segregation (CQRS)](https://docs.microsoft.com/en-us/azure/architecture/patterns/cqrs)を適用して分離されます。

![](docs/Images/CQRS.jpg)

Commands are processed using _Write Model_ which is implemented using DDD tactical patterns:

コマンドは、DDD の戦術パターンで実装された*Write Model*を用いて処理されます。

```csharp
internal class CreateNewMeetingGroupCommandHandler : ICommandHandler<CreateNewMeetingGroupCommand>
{
    private readonly IMeetingGroupRepository _meetingGroupRepository;
    private readonly IMeetingGroupProposalRepository _meetingGroupProposalRepository;

    internal CreateNewMeetingGroupCommandHandler(
        IMeetingGroupRepository meetingGroupRepository,
        IMeetingGroupProposalRepository meetingGroupProposalRepository)
    {
        _meetingGroupRepository = meetingGroupRepository;
        _meetingGroupProposalRepository = meetingGroupProposalRepository;
    }

    public async Task<Unit> Handle(CreateNewMeetingGroupCommand request, CancellationToken cancellationToken)
    {
        var meetingGroupProposal = await _meetingGroupProposalRepository.GetByIdAsync(request.MeetingGroupProposalId);

        var meetingGroup = meetingGroupProposal.CreateMeetingGroup();

        await _meetingGroupRepository.AddAsync(meetingGroup);

        return Unit.Value;
    }
}
```

Queries are processed using _Read Model_ which is implemented by executing raw SQL statements on database views:

クエリは、データベースのビューに対して生の SQL 文を実行することで実装される*Read Model*を用いて処理されます。

```csharp
internal class GetAllMeetingGroupsQueryHandler : IQueryHandler<GetAllMeetingGroupsQuery, List<MeetingGroupDto>>
{
    private readonly ISqlConnectionFactory _sqlConnectionFactory;

    internal GetAllMeetingGroupsQueryHandler(ISqlConnectionFactory sqlConnectionFactory)
    {
        _sqlConnectionFactory = sqlConnectionFactory;
    }

    public async Task<List<MeetingGroupDto>> Handle(GetAllMeetingGroupsQuery request, CancellationToken cancellationToken)
    {
        var connection = _sqlConnectionFactory.GetOpenConnection();

        const string sql = "SELECT " +
                           "[MeetingGroup].[Id], " +
                           "[MeetingGroup].[Name], " +
                           "[MeetingGroup].[Description], " +
                           "[MeetingGroup].[LocationCountryCode], " +
                           "[MeetingGroup].[LocationCity]" +
                           "FROM [meetings].[v_MeetingGroups] AS [MeetingGroup]";
        var meetingGroups = await connection.QueryAsync<MeetingGroupDto>(sql);

        return meetingGroups.AsList();
    }
}
```

**Key advantages:**

**主な利点:**

- Solution is appropriate to the problem - reading and writing needs are usually different
- Supports [Single Responsibility Principle](https://en.wikipedia.org/wiki/Single_responsibility_principle) (SRP) - one handler does one thing
- Supports [Interface Segregation Principle](https://en.wikipedia.org/wiki/Interface_segregation_principle) (ISP) - each handler implements interface with exactly one method
- Supports [Parameter Object pattern](https://refactoring.com/catalog/introduceParameterObject.html) - Commands and Queries are objects which are easy to serialize/deserialize
- Easy way to apply [Decorator pattern](https://en.wikipedia.org/wiki/Decorator_pattern) to handle cross-cutting concerns
- Supports Loose Coupling by use of the [Mediator pattern](https://en.wikipedia.org/wiki/Mediator_pattern) - separates invoker of request from handler of request

- 問題に適したソリューション - 読み書きのニーズは通常異なる
- 単一責任原則](https://en.wikipedia.org/wiki/Single_responsibility_principle) (SRP)をサポート - 1 つのハンドラが 1 つのことを行う。
- Interface Segregation Principle](https://en.wikipedia.org/wiki/Interface_segregation_principle) (ISP)をサポート - 各ハンドラは、正確に 1 つのメソッドでインタフェースを実装する。
- Parameter Object パターン](https://refactoring.com/catalog/introduceParameterObject.html)に対応 - コマンドやクエリーはシリアライズ/デシリアライズしやすいオブジェクトです。
- Decorator パターン](https://en.wikipedia.org/wiki/Decorator_pattern)の適用が容易で、横断的な関心事を扱うことができます。
- Mediator パターン](https://en.wikipedia.org/wiki/Mediator_pattern)を用いたLoose Coupling のサポート - リクエストの起動者とリクエストの処理者を分離します。

**Disadvantage:**

**デメリット：\***。

- Mediator pattern introduces extra indirection and is harder to reason about which class handles the request

For more information: [Simple CQRS implementation with raw SQL and DDD](https://www.kamilgrzybek.com/design/simple-cqrs-implementation-with-raw-sql-and-ddd/)

- Mediator パターンでは、余分なインダイレクションが発生し、どのクラスがリクエストを処理するかを推論するのが難しくなります。

詳細はこちらをご覧ください。[Simple CQRS implementation with raw SQL and DDD](https://www.kamilgrzybek.com/design/simple-cqrs-implementation-with-raw-sql-and-ddd/)

### 3.5 Domain Model Principles and Attributes

### 3.5 ドメインモデルの原則と属性

The Domain Model, which is the central and most critical part in the system, should be designed with special attention. Here are some key principles and attributes which are applied to Domain Models of each module:

ドメイン・モデルは、システムの中心となる最も重要な部分であり、特に注意して設計する必要があります。ここでは、各モジュールのドメインモデルに適用される主要な原則と属性を紹介します。

1. **High level of encapsulation**

   All members are `private` by default, then `internal` - only `public` at the very edge.

2. **High level of PI (Persistence Ignorance)**

   No dependencies to infrastructure, databases, etc. All classes are [POCOs](https://en.wikipedia.org/wiki/Plain_old_CLR_object).

3. **Rich in behavior**

   All business logic is located in the Domain Model. No leaks to the application layer or elsewhere.

4. **Low level of Primitive Obsession**

   Primitive attributes of Entites grouped together using ValueObjects.

5. **Business language**

   All classes, methods and other members are named in business language used in this Bounded Context.

6. **Testable**

   The Domain Model is a critical part of the system so it should be easy to test (Testable Design).

7. 1. **高いレベルのカプセル化**。

   すべてのメンバーは、デフォルトでは `private` 、次に `internal` 、そしてギリギリのところで `public` となります。

8. 2. **ハイレベルな PI(Persistence Ignorance)**。

   インフラやデータベースなどへの依存はありません。すべてのクラスは[POCOs](https://en.wikipedia.org/wiki/Plain_old_CLR_object)です。

9. 3. **動作が豊富**。

   すべてのビジネスロジックはドメインモデルにあります。アプリケーション層などへのリークはありません。

10. 4. **低レベルのプリミティブ・オブセッション** (Primitive Obsession)

    Entite のプリミティブな属性は、ValueObject を使ってグループ化されています。

11. 5. **ビジネス言語**。

    すべてのクラス、メソッド、およびその他のメンバーは、この Bounded Context で使用されるビジネス言語で命名される。

12. 6. **テスト可能**。

    ドメインモデルはシステムの重要な部分であるため、テストしやすいものでなければなりません（Testable Design）。

```csharp
public class MeetingGroup : Entity, IAggregateRoot
{
    public MeetingGroupId Id { get; private set; }

    private string _name;

    private string _description;

    private MeetingGroupLocation _location;

    private MemberId _creatorId;

    private List<MeetingGroupMember> _members;

    private DateTime _createDate;

    private DateTime? _paymentDateTo;

    internal static MeetingGroup CreateBasedOnProposal(
        MeetingGroupProposalId meetingGroupProposalId,
        string name,
        string description,
        MeetingGroupLocation location, MemberId creatorId)
    {
        return new MeetingGroup(meetingGroupProposalId, name, description, location, creatorId);
    }

     public Meeting CreateMeeting(
            string title,
            MeetingTerm term,
            string description,
            MeetingLocation location,
            int? attendeesLimit,
            int guestsLimit,
            Term rsvpTerm,
            MoneyValue eventFee,
            List<MemberId> hostsMembersIds,
            MemberId creatorId)
        {
            this.CheckRule(new MeetingCanBeOrganizedOnlyByPayedGroupRule(_paymentDateTo));

            this.CheckRule(new MeetingHostMustBeAMeetingGroupMemberRule(creatorId, hostsMembersIds, _members));

            return new Meeting(this.Id,
                title,
                term,
                description,
                location,
                attendeesLimit,
                guestsLimit,
                rsvpTerm,
                eventFee,
                hostsMembersIds,
                creatorId);
        }
```

### 3.6 Cross-Cutting Concerns

### 3.6 横断的な懸念事項

To support [Single Responsibility Principle](https://en.wikipedia.org/wiki/Single_responsibility_principle) and [Don't Repeat Yourself](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) principles, the implementation of cross-cutting concerns is done using the [Decorator Pattern](https://en.wikipedia.org/wiki/Decorator_pattern). Each Command processor is decorated by 3 decorators: logging, validation and unit of work.

単一責任原則](https://en.wikipedia.org/wiki/Single_responsibility_principle)と[Don't Repeat Yourself](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)の原則をサポートするために、横断的な懸念の実装は[Decorator Pattern](https://en.wikipedia.org/wiki/Decorator_pattern)を使用しています。各コマンドプロセッサは、ロギング、バリデーション、ユニットオブワークの3つのデコレータで装飾されています。

![](docs/Images/Decorator.jpg)

**Logging**

**ロギング**（Logging

The Logging decorator logs execution, arguments and processing of each Command. This way each log inside a processor has the log context of the processing command.

Logging デコレーターは、各 Command の実行、引数、および処理を記録します。これにより、プロセッサ内の各ログは、処理中のコマンドのログコンテキストを持ちます。

```csharp
internal class LoggingCommandHandlerDecorator<T> : ICommandHandler<T> where T:ICommand
{
    private readonly ILogger _logger;
    private readonly IExecutionContextAccessor _executionContextAccessor;
    private readonly ICommandHandler<T> _decorated;

    public LoggingCommandHandlerDecorator(
        ILogger logger,
        IExecutionContextAccessor executionContextAccessor,
        ICommandHandler<T> decorated)
    {
        _logger = logger;
        _executionContextAccessor = executionContextAccessor;
        _decorated = decorated;
    }
    public async Task<Unit> Handle(T command, CancellationToken cancellationToken)
    {
        if (command is IRecurringCommand)
        {
            return await _decorated.Handle(command, cancellationToken);
        }
        using (
            LogContext.Push(
                new RequestLogEnricher(_executionContextAccessor),
                new CommandLogEnricher(command)))
        {
            try
            {
                this._logger.Information(
                    "Executing command {Command}",
                    command.GetType().Name);

                var result = await _decorated.Handle(command, cancellationToken);

                this._logger.Information("Command {Command} processed successful", command.GetType().Name);

                return result;
            }
            catch (Exception exception)
            {
                this._logger.Error(exception, "Command {Command} processing failed", command.GetType().Name);
                throw;
            }
        }
    }

    private class CommandLogEnricher : ILogEventEnricher
    {
        private readonly ICommand _command;

        public CommandLogEnricher(ICommand command)
        {
            _command = command;
        }
        public void Enrich(LogEvent logEvent, ILogEventPropertyFactory propertyFactory)
        {
            logEvent.AddOrUpdateProperty(new LogEventProperty("Context", new ScalarValue($"Command:{_command.Id.ToString()}")));
        }
    }

    private class RequestLogEnricher : ILogEventEnricher
    {
        private readonly IExecutionContextAccessor _executionContextAccessor;
        public RequestLogEnricher(IExecutionContextAccessor executionContextAccessor)
        {
            _executionContextAccessor = executionContextAccessor;
        }
        public void Enrich(LogEvent logEvent, ILogEventPropertyFactory propertyFactory)
        {
            if (_executionContextAccessor.IsAvailable)
            {
                logEvent.AddOrUpdateProperty(new LogEventProperty("CorrelationId", new ScalarValue(_executionContextAccessor.CorrelationId)));
            }
        }
    }
}
```

**Validation**

**Validation** (バリデーション)

The Validation decorator performs Command data validation. It checks rules against Command arguments using the FluentValidation library.

Validation デコレーターは、Command のデータ検証を行います。FluentValidation ライブラリを使って、Command の引数に対してルールをチェックします。

```csharp
internal class ValidationCommandHandlerDecorator<T> : ICommandHandler<T> where T:ICommand
{
    private readonly IList<IValidator<T>> _validators;
    private readonly ICommandHandler<T> _decorated;

    public ValidationCommandHandlerDecorator(
        IList<IValidator<T>> validators,
        ICommandHandler<T> decorated)
    {
        this._validators = validators;
        _decorated = decorated;
    }

    public Task<Unit> Handle(T command, CancellationToken cancellationToken)
    {
        var errors = _validators
            .Select(v => v.Validate(command))
            .SelectMany(result => result.Errors)
            .Where(error => error != null)
            .ToList();

        if (errors.Any())
        {
            var errorBuilder = new StringBuilder();

            errorBuilder.AppendLine("Invalid command, reason: ");

            foreach (var error in errors)
            {
                errorBuilder.AppendLine(error.ErrorMessage);
            }

            throw new InvalidCommandException(errorBuilder.ToString(), null);
        }

        return _decorated.Handle(command, cancellationToken);
    }
}
```

**Unit Of Work**

**仕事の単位**。

All Command processing has side effects. To avoid calling commit on every handler, `UnitOfWorkCommandHandlerDecorator` is used. It additionally marks `InternalCommand` as processed (if it is Internal Command) and dispatches all Domain Events (as part of [Unit Of Work](https://martinfowler.com/eaaCatalog/unitOfWork.html)).

すべてのコマンド処理には副作用があります。すべてのハンドラーのコミットを避けるために、`UnitOfWorkCommandHandlerDecorator`を使用します。これはさらに、`InternalCommand` が処理されたとマークし(内部コマンドの場合)、すべてのドメインイベントをディスパッチします([Unit Of Work](https://martinfowler.com/eaaCatalog/unitOfWork.html)の一部として)。

```csharp
public class UnitOfWorkCommandHandlerDecorator<T> : ICommandHandler<T> where T:ICommand
{
    private readonly ICommandHandler<T> _decorated;
    private readonly IUnitOfWork _unitOfWork;
    private readonly MeetingsContext _meetingContext;

    public UnitOfWorkCommandHandlerDecorator(
        ICommandHandler<T> decorated,
        IUnitOfWork unitOfWork,
        MeetingsContext meetingContext)
    {
        _decorated = decorated;
        _unitOfWork = unitOfWork;
        _meetingContext = meetingContext;
    }

    public async Task<Unit> Handle(T command, CancellationToken cancellationToken)
    {
        await this._decorated.Handle(command, cancellationToken);

        if (command is InternalCommandBase)
        {
            var internalCommand =
                await _meetingContext.InternalCommands.FirstOrDefaultAsync(x => x.Id == command.Id,
                    cancellationToken: cancellationToken);

            if (internalCommand != null)
            {
                internalCommand.ProcessedDate = DateTime.UtcNow;
            }
        }

        await this._unitOfWork.CommitAsync(cancellationToken);

        return Unit.Value;
    }
}
```

### 3.7 Modules Integration

### 3.7 モジュールの統合

Integration between modules is strictly **asynchronous** using Integration Events and the In Memory Event Bus as broker. In this way coupling between modules is minimal and exists only on the structure of Integration Events.

モジュール間の統合は、Integration Events と In Memory Event Bus をブローカーとして使用し、厳密に **非同期** に行われます。この方法では、モジュール間の結合は最小限に抑えられ、統合イベントの構造にのみ存在します。

**Modules don't share data** so it is not possible nor desirable to create a transaction which spans more than one module. To ensure maximum reliability, the [Outbox / Inbox pattern](http://www.kamilgrzybek.com/design/the-outbox-pattern/) is used. This pattern provides accordingly _"At-Least-Once delivery"_ and _"At-Least-Once processing"_.

\*\*モジュールはデータを共有しないため、複数のモジュールにまたがるトランザクションを作成することはできませんし、望ましくもありません。最大限の信頼性を確保するために、[Outbox / Inbox パターン](http://www.kamilgrzybek.com/design/the-outbox-pattern/)が使用されます。このパターンは、それに応じて _"At-Least-Once delivery" _ および _"At-Least-Once processing" _ を提供します。

![](docs/Images/OutboxInbox.jpg)

The Outbox and Inbox is implemented using two SQL tables and a background worker for each module. The background worker is implemented using the Quartz.NET library.

Outbox と Inbox は、2 つの SQL テーブルと、各モジュールのバックグラウンドワーカーを使って実装されています。バックグラウンドワーカーは、Quartz.NET ライブラリを使用して実装されています。

**Saving to Outbox:**

**Outbox への保存：**。

![](docs/Images/OutboxSave.png)

**Processing Outbox:**

**アウトボックスの処理：**?

![](docs/Images/OutboxProcessing.png)

### 3.8 Internal Processing

### 3.8 内部処理

The main principle of this system is that you can change its state only by calling a specific Command.

このシステムの大原則は、特定のコマンドを呼び出すことによってのみ、その状態を変化させることができるということです。

Commands can be called not only by the API, but by the processing module itself. The main use case which implements this mechanism is data processing in eventual consistency mode when we want to process something in a different process and transaction. This applies, for example, to Inbox processing because we want to do something (calling a Command) based on an Integration Event from the Inbox.

コマンドは API からだけでなく、処理モジュール自身からも呼び出すことができます。このメカニズムを実装した主なユースケースは、異なるプロセスやトランザクションで何かを処理したい場合の、最終的な一貫性モードでのデータ処理です。これは例えば、受信トレイからの統合イベントに基づいて何かを行いたい（コマンドを呼び出したい）場合の受信トレイの処理に適用されます。

This idea is taken from Alberto's Brandolini's Event Storming picture called "The picture that explains “almost” everything" which shows that every side effect (domain event) is created by invoking a Command on Aggregate. See [EventStorming cheat sheet](https://xebia.com/blog/eventstorming-cheat-sheet/) article for more details.

このアイデアは、Alberto's Brandolini 氏の Event Storming の写真「The picture that explains "almost" everything」から引用されています。この写真では、すべての副作用（ドメインイベント）が Aggregate 上で Command を呼び出すことによって作成されることが示されています。詳細は[EventStorming cheat sheet](https://xebia.com/blog/eventstorming-cheat-sheet/)の記事を参照してください。

Implementation of internal processing is very similar to implementation of the Outbox and Inbox. One SQL table and one background worker for processing. Each internally processing Command must inherit from `InternalCommandBase` class:

内部処理の実装は、Outbox と Inbox の実装と非常によく似ています。1 つの SQL テーブルと 1 つのバックグラウンドワーカーで処理を行います。内部処理を行う各コマンドは、`InternalCommandBase`クラスを継承する必要があります。

```csharp
internal abstract class InternalCommandBase : ICommand
{
    public Guid Id { get; }

    protected InternalCommandBase(Guid id)
    {
        this.Id = id;
    }
}
```

This is important because the `UnitOfWorkCommandHandlerDecorator` must mark an internal Command as processed during committing:

これは重要なことで、`UnitOfWorkCommandHandlerDecorator`はコミット時に内部のコマンドを処理済みとしてマークしなければなりません。

```csharp
public async Task<Unit> Handle(T command, CancellationToken cancellationToken)
{
    await this._decorated.Handle(command, cancellationToken);

    if (command is InternalCommandBase)
    {
        var internalCommand =
            await _meetingContext.InternalCommands.FirstOrDefaultAsync(x => x.Id == command.Id,
                cancellationToken: cancellationToken);

        if (internalCommand != null)
        {
            internalCommand.ProcessedDate = DateTime.UtcNow;
        }
    }

    await this._unitOfWork.CommitAsync(cancellationToken);

    return Unit.Value;
}
```

### 3.9 Security

### 3.9 セキュリティ

**Authentication**

**認証\***について

Authentication is implemented using JWT Token and Bearer scheme using IdentityServer. For now, only one authentication method is implemented: forms style authentication (username and password) via the OAuth2 [Resource Owner Password Grant Type](https://www.oauth.com/oauth2-servers/access-tokens/password-grant/). It requires implementation of the `IResourceOwnerPasswordValidator` interface:

認証は IdentityServer による JWT トークンと Bearer スキームで実装しています。現時点では、OAuth2 [Resource Owner Password Grant Type](https://www.oauth.com/oauth2-servers/access-tokens/password-grant/)によるフォーム形式の認証(ユーザー名とパスワード)のみが実装されています。これには `IResourceOwnerPasswordValidator` インターフェースの実装が必要です。

```csharp
public class ResourceOwnerPasswordValidator : IResourceOwnerPasswordValidator
{
    private readonly IUserAccessModule _userAccessModule;

    public ResourceOwnerPasswordValidator(IUserAccessModule userAccessModule)
    {
        _userAccessModule = userAccessModule;
    }

    public async Task ValidateAsync(ResourceOwnerPasswordValidationContext context)
    {
        var authenticationResult = await _userAccessModule.ExecuteCommandAsync(new AuthenticateCommand(context.UserName, context.Password));
        if (!authenticationResult.IsAuthenticated)
        {
            context.Result = new GrantValidationResult(
                TokenRequestErrors.InvalidGrant,
                authenticationResult.AuthenticationError);
            return;
        }
        context.Result = new GrantValidationResult(
            authenticationResult.User.Id.ToString(),
            "forms",
            authenticationResult.User.Claims);
    }
}
```

**Authorization**

**認可**について

Authorization is achieved by implementing [RBAC (Role Based Access Control)](https://en.wikipedia.org/wiki/Role-based_access_control) using Permissions. Permissions are more granular and a much better way to secure your application than Roles alone. Each User has a set of Roles and each Role contains one or more Permission. The User's set of Permissions is extracted from all Roles the User belongs to. Permissions are always checked on `Controller` level - never Roles:

認可は、パーミッションを使って[RBAC (Role Based Access Control)](https://en.wikipedia.org/wiki/Role-based_access_control)を実装することで実現します。パーミッションはより詳細で、ロールだけよりもはるかに優れた方法でアプリケーションを保護します。各ユーザーはロールのセットを持ち、各ロールには 1 つ以上のパーミッションが含まれます。ユーザのパーミッションのセットは、そのユーザが所属するすべてのロールから抽出されます。パーミッションは常に `Controller` レベルでチェックされ、ロールはチェックされません。

```csharp
[HttpPost]
[Route("")]
[HasPermission(MeetingsPermissions.ProposeMeetingGroup)]
public async Task<IActionResult> ProposeMeetingGroup(ProposeMeetingGroupRequest request)
{
    await _meetingsModule.ExecuteCommandAsync(
        new ProposeMeetingGroupCommand(
            request.Name,
            request.Description,
            request.LocationCity,
            request.LocationCountryCode));

    return Ok();
}
```

### 3.10 Unit Tests

### 3.10 ユニットテスト

**Definition:**

**定義：**。

> A unit test is an automated piece of code that invokes the unit of work being tested, and then checks some assumptions about a single end result of that unit. A unit test is almost always written using a unit testing framework. It can be written easily and runs quickly. It’s trustworthy, readable, and maintainable. It’s consistent in its results as long as production code hasn’t changed. [Art of Unit Testing 2nd Edition](https://www.manning.com/books/the-art-of-unit-testing-second-edition) Roy Osherove

> ユニットテストとは、テスト対象のユニットを起動し、そのユニットの最終結果に関するいくつかの仮定をチェックする自動化されたコードの一部のことです。ユニットテストは、ほとんどの場合、ユニットテストフレームワークを使って書かれます。簡単に書けて、すぐに実行できます。信頼性が高く、読みやすく、保守性に優れています。プロダクションコードが変更されていない限り、結果に一貫性があります。[ユニットテストの技術 第 2 版](https://www.manning.com/books/the-art-of-unit-testing-second-edition) Roy Osherove

**Attributes of good unit test**

\*\*良いユニットテストの属性

- Automated
- Maintainable
- Runs very fast (in ms)
- Consistent, Deterministic (always the same result)
- Isolated from other tests
- Readable
- Can be executed by anyone
- Testing public API, not internal behavior (overspecification)
- Looks like production code
- Treated as production code

- 自動化されている
- 維持可能
- 非常に高速に実行される(ms 単位)
- Consistent, Deterministic (常に同じ結果が得られる)
- 他のテストから隔離されている
- 読み取り可能
- 誰でも実行可能
- 内部動作ではなく、公開 API をテストする（オーバースペック
- 製品コードのように見える
- 製品コードとして扱われる

**Implementation**

\*\*実現のために

Unit tests should mainly test business logic (domain model): </br>

ユニットテストでは、主にビジネスロジック（ドメインモデル）をテストする必要があります。</br>

![](docs/Images/unit_tests.jpg)

Each unit test has 3 standard sections: Arrange, Act and Assert:

各ユニットテストには 3 つの標準的なセクションがあります。Arrange, Act, Assert です。

![](docs/Images/UnitTestsGeneral.jpg)

**1\. Arrange**

**1\. Arrange**（アレンジ

The Arrange section is responsible for preparing the Aggregate for testing the public method that we want to test. This public method is often called (from the unit tests perspective) the SUT (system under test).

Arrange セクションは、テストしたいパブリックメソッドをテストするために Aggregate を準備する役割があります。このパブリックメソッドは、(ユニットテストの観点から)SUT(system under test)と呼ばれることが多いです。

Creating an Aggregate ready for testing involves **calling one or more other public constructors/methods** on the Domain Model. At first it may seem that we are testing too many things at the same time, but this is not true. We need to be one hundred percent sure that the Aggregate is in a state exactly as it will be in production. This can only be ensured when we:

テストの準備ができた Aggregate を作成するには、ドメインモデル上の 1 つまたは複数の他のパブリックコンストラクタ/メソッド\*\*を呼び出す必要があります。最初は、同時に多くのことをテストしているように見えるかもしれませんが、そうではありません。しかし、これは間違いです。私たちは、Aggregate が実際の運用時と同じ状態であることを 100％確認する必要があります。これを確実にするには、次のことが必要です。

- **Use only public API of Domain Model**

- ドメインモデルのパブリック API のみを使用する\*\*。

- Don't use [InternalsVisibleToAttribute](https://docs.microsoft.com/en-us/dotnet/api/system.runtime.compilerservices.internalsvisibletoattribute?view=netframework-4.8) class
  - This exposes the Domain Model to the Unit Tests library, removing encapsulation so our tests and production code are treated differently and it is a very bad thing
- Don't use [ConditionalAttribute](https://docs.microsoft.com/en-us/dotnet/api/system.diagnostics.conditionalattribute?view=netframework-4.8) classes - it reduces readability and increases complexity
- Don't create any special constructors/factory methods for tests (even with conditional compilation symbols)
  - Special constructor/factory method only for unit tests causes duplication of business logic in the test itself and focuses on state - this kind of approach causes the test to be very sensitive to changes and hard to maintain
- Don't remove encapsulation from Domain Model (for example: change keywords from `internal`/`private` to `public`)
- Don't make methods `protected` to inherit from tested class and in this way provide access to internal methods/properties

- ドメインモデルのパブリック API のみを使用する\*\*。
- InternalsVisibleToAttribute](https://docs.microsoft.com/en-us/dotnet/api/system.runtime.compilerservices.internalsvisibletoattribute?view=netframework-4.8)クラスを使用しない。
  - これは、ドメインモデルをユニットテストライブラリに公開し、カプセル化を解除してしまうため、テストと本番コードが異なって扱われてしまい、非常にまずいことになります。
- ConditionalAttribute](https://docs.microsoft.com/en-us/dotnet/api/system.diagnostics.conditionalattribute?view=netframework-4.8)クラスは使わないでください - 読みやすさが損なわれ、複雑さが増します。
- テスト用の特別なコンストラクタやファクトリメソッドを作らないでください (条件付きコンパイルシンボルを使っても)。
  - ユニットテストのためだけに特別なコンストラクタやファクトリメソッドを作ると、テスト自体にビジネスロジックが重複してしまい、状態に焦点が当たってしまいます。このようなアプローチは、テストが変更に非常に敏感になり、メンテナンスが難しくなります。
- ドメインモデルからカプセル化を取り除いてはいけません (例: キーワードを `internal`/`private` から `public` に変更する)
- テストされたクラスを継承するために、メソッドを `protected` にして、内部のメソッドやプロパティへのアクセスを提供してはいけません。

**Isolation of external dependencies**

\*\*外部依存性の隔離

There are 2 main concepts - stubs and mocks:

スタブとモックという 2 つの主要な概念があります。

> A stub is a controllable replacement for an existing dependency (or collaborator) in the system. By using a stub, you can test your code without dealing with the dependency directly.

> スタブとは、システム内の既存の依存関係（または協力者）を制御可能な形で置き換えるものです。スタブを使うことで、依存関係を直接扱うことなくコードをテストすることができます。

> A mock object is a fake object in the system that decides whether the unit test has passed or failed. It does so by verifying whether the object under test called the fake object as expected. There’s usually no more than one mock per test.
> [Art of Unit Testing 2nd Edition](https://www.manning.com/books/the-art-of-unit-testing-second-edition) Roy Osherove

> モックオブジェクトとは、ユニットテストが成功したか失敗したかを判断する、システム内の偽のオブジェクトです。モックオブジェクトは、テスト対象のオブジェクトが期待通りにフェイクオブジェクトを呼び出したかどうかを検証することで、ユニットテストの合否を決定します。通常、1 つのテストに 1 つ以上のモックはありません。
> [ユニットテストの技術 第 2 版](https://www.manning.com/books/the-art-of-unit-testing-second-edition) Roy Osherove

Good advice: use stubs if you need to, but try to avoid mocks. Mocking causes us to test too many internal things and leads to overspecification.

いいアドバイスですね。必要ならスタブを使いますが、モックはなるべく避けたほうがいいでしょう。モックを使うと、内部のテストが多くなりすぎて、オーバースペックになってしまいます。

**2\. Act**

This section is very easy - we execute **exactly one** public method on aggregate (SUT).

このセクションはとても簡単だ。集合体(SUT)上で**正確に 1 つ**のパブリックメソッドを実行する。

**3\. Assert**

In this section we check expectations. There are only 2 possible outcomes:

- Method completed and Domain Event(s) published
- Business rule was broken

このセクションでは、期待値をチェックします。可能な結果は 2 つだけです。

- メソッドが完了し、ドメインイベントが発行された場合
- ビジネスルールの違反

Simple example:

```csharp
[Test]
public void NewUserRegistration_WithUniqueLogin_IsSuccessful()
{
    // Arrange
    var usersCounter = Substitute.For<IUsersCounter>();

    // Act
    var userRegistration =
        UserRegistration.RegisterNewUser(
            "login", "password", "test@email",
            "firstName", "lastName", usersCounter);

    // Assert
    var newUserRegisteredDomainEvent = AssertPublishedDomainEvent<NewUserRegisteredDomainEvent>(userRegistration);
    Assert.That(newUserRegisteredDomainEvent.UserRegistrationId, Is.EqualTo(userRegistration.Id));
}

[Test]
public void NewUserRegistration_WithoutUniqueLogin_BreaksUserLoginMustBeUniqueRule()
{
    // Arrange
    var usersCounter = Substitute.For<IUsersCounter>();
    usersCounter.CountUsersWithLogin("login").Returns(x => 1);

    // Assert
    AssertBrokenRule<UserLoginMustBeUniqueRule>(() =>
    {
        // Act
        UserRegistration.RegisterNewUser(
            "login", "password", "test@email",
            "firstName", "lastName", usersCounter);
    });
}
```

Advanced example:

```csharp
[Test]
public void AddAttendee_WhenMemberIsAlreadyAttendeeOfMeeting_IsNotPossible()
{
    // Arrange
    var creatorId = new MemberId(Guid.NewGuid());
    var meetingTestData = CreateMeetingTestData(new MeetingTestDataOptions
    {
        CreatorId = creatorId
    });
    var newMemberId = new MemberId(Guid.NewGuid());
    meetingTestData.MeetingGroup.JoinToGroupMember(newMemberId);
    meetingTestData.Meeting.AddAttendee(meetingTestData.MeetingGroup, newMemberId, 0);

    // Assert
    AssertBrokenRule<MemberCannotBeAnAttendeeOfMeetingMoreThanOnceRule>(() =>
    {
        // Act
        meetingTestData.Meeting.AddAttendee(meetingTestData.MeetingGroup, newMemberId, 0);
    });
}
```

`CreateMeetingTestData` method is an implementation of [SUT Factory](https://blog.ploeh.dk/2009/02/13/SUTFactory/) described by Mark Seemann which allows keeping common creation logic in one place:

CreateMeetingTestData`メソッドは、Mark Seemann 氏によって記述された[SUT Factory](https://blog.ploeh.dk/2009/02/13/SUTFactory/)の実装であり、共通の作成ロジックを一か所にまとめることができます。

```csharp
protected MeetingTestData CreateMeetingTestData(MeetingTestDataOptions options)
{
    var proposalMemberId = options.CreatorId ?? new MemberId(Guid.NewGuid());
    var meetingProposal = MeetingGroupProposal.ProposeNew(
        "name", "description",
        new MeetingGroupLocation("Warsaw", "PL"), proposalMemberId);

    meetingProposal.Accept();

    var meetingGroup = meetingProposal.CreateMeetingGroup();

    meetingGroup.UpdatePaymentInfo(DateTime.Now.AddDays(1));

    var meetingTerm = options.MeetingTerm ??
                      new MeetingTerm(DateTime.UtcNow.AddDays(1), DateTime.UtcNow.AddDays(2));

    var rsvpTerm = options.RvspTerm ?? Term.NoTerm;
    var meeting = meetingGroup.CreateMeeting("title",
        meetingTerm,
        "description",
        new MeetingLocation("Name", "Address", "PostalCode", "City"),
        options.AttendeesLimit,
        options.GuestsLimit,
        rsvpTerm,
        MoneyValue.Zero,
        new List<MemberId>(),
        proposalMemberId);

    DomainEventsTestHelper.ClearAllDomainEvents(meetingGroup);

    return new MeetingTestData(meetingGroup, meeting);
}
```

### 3.11 Architecture Decision Log

### 3.11 アーキテクチャ決定ログ

All Architectural Decisions (AD) are documented in the [Architecture Decision Log (ADL)](docs/architecture-decision-log).

すべてのアーキテクチャ決定 (AD) は、[アーキテクチャ決定ログ (ADL)](docs/architecture-decision-log) で文書化されます。

More information about documenting architecture-related decisions in this way : [https://github.com/joelparkerhenderson/architecture_decision_record](https://github.com/joelparkerhenderson/architecture_decision_record)

アーキテクチャー関連の決定事項をこのように文書化することについての詳しい情報は、[https://github.com/joelparkerhenderson/architecture_decision_record](https://github.com/joelparkerhenderson/architecture_decision_record)をご覧ください。

### 3.12 Architecture Unit Tests

### 3.12 アーキテクチャのユニットテスト

In some cases it is not possible to enforce the application architecture, design or established conventions using compiler (compile-time). For this reason, code implementations can diverge from the original design and architecture. We want to minimize this behavior, not only by code review.</br>

アプリケーションのアーキテクチャや設計、確立された規約をコンパイラ(コンパイル時)で強制することができない場合があります。そのため、コードの実装が本来の設計やアーキテクチャから乖離することがあります。私たちは、コード レビューだけでなく、このような動作を最小限に抑えたいと考えています。

To do this, unit tests of system architecture, design, major conventions and assumptions have been written. In .NET there is special library for this task: [NetArchTest](https://github.com/BenMorris/NetArchTest). This library has been written based on the very popular JAVA architecture unit tests library - [ArchUnit](https://www.archunit.org/).</br>

そのために、システムのアーキテクチャ、設計、主要な規約や前提条件のユニットテストが書かれています。.NET には、このタスクのための特別なライブラリがあります。[NetArchTest](https://github.com/BenMorris/NetArchTest)です。このライブラリは、非常に人気のある JAVA アーキテクチャ ユニット テスト ライブラリである [ArchUnit](https://www.archunit.org/) をベースに作成されています。

Using this kind of tests we can test proper layering of our application, dependencies, encapsulation, immutability, DDD correct implementation, naming, conventions and so on - everything what we need to test. Example:</br>

この種のテストを使用すると、アプリケーションの適切なレイヤリング、依存関係、カプセル化、不変性、DDD の正しい実装、ネーミング、規約など、テストが必要なものすべてをテストすることができます。例：</br> <br

![](docs/Images/architecture_unit_tests.png)

More information about architecture unit tests here: [https://blogs.oracle.com/javamagazine/unit-test-your-architecture-with-archunit](https://blogs.oracle.com/javamagazine/unit-test-your-architecture-with-archunit)

### 3.13 Integration Tests

### 3.13 統合テスト

#### Definition

#### 定義

"Integration Test" term is blurred. It can mean test between classes, modules, services, even systems - see [this](https://martinfowler.com/bliki/IntegrationTest.html) article (by Martin Fowler). </br>

「統合テスト」という言葉は曖昧です。クラス、モジュール、サービス、さらにはシステム間のテストを意味することもあります。</br>。

For this reason, the definition of integration test in this project is as follows:</br>

この理由から、このプロジェクトでの統合テストの定義は次のようになります。

- it verifies how system works in integration with "out-of-process" dependencies - database, messaging system, file system or external API
- it tests particular use case
- it can be slow (as opposed to Unit Test)

- システムが「プロセス外」の依存関係 (データベース、メッセージング システム、ファイル システム、または外部 API) との統合でどのように動作するかを検証する。
- 特定の使用例をテストする。
- 時間がかかることがある (ユニット テストとは対照的に)

#### Approach

#### アプローチ

- **Do not mock dependencies over which you have full control** (like database). Full control dependency means you can always revert all changes (remove side-effects) and no one can notice it. They are not visible to others. See next point, please.
- **Use "production", normal, real database version**. Some use e.g. in memory repository, some use light databases instead "production" version. This is still mocking. Testing makes sense if we have full confidence in testing. You can't trust the test if you know that the infrastructure in the production environment will vary. Be always as close to production environment as possible.
- **Mock dependencies over which you don't have control**. No control dependency means you can't remove side-effects after interaction with this dependency (external API, messaging system, SMTP server etc.). They can be visible to others.

- 完全にコントロールできる依存関係\*\*（データベースなど）をモックしてはいけません。完全にコントロールできる依存関係とは、常にすべての変更を元に戻す（副作用を取り除く）ことができ、誰にも気づかれないことを意味します。他の人からは見えないのです。次のポイントを参照してください。
- **"production"、通常の、実際のデータベースバージョンを使用してください**。ある人はメモリ内のリポジトリを使い、ある人は "production "バージョンの代わりにライトデータベースを使います。これはまだモックです。テストは、テストに対する完全な信頼があれば意味があります。本番環境のインフラが異なることがわかっている場合、テストを信頼することはできません。可能な限り本番環境に近づけてください。
- コントロールできない依存関係をモックする\*\*。制御できない依存関係とは、その依存関係（外部 API、メッセージングシステム、SMTP サーバなど）とのやりとりの後に、副作用を取り除くことができないことを意味します。これらは、他の人から見えることがあります。

#### Implementation

#### 実装

Integration test should test exactly one use case. One use case is represented by one Command/Query processing so CommandHandler/QueryHandler in Application layer is perfect starting point for running the Integration Test:</br>

統合テストでは、正確に 1 つのユースケースをテストする必要があります。1 つのユースケースは、1 つの Command/Query 処理で表されるため、アプリケーション層の CommandHandler/QueryHandler は、統合テストを実行するための完璧な出発点となります: </br>。

![](docs/Images/integration_tests.jpg)
For each test, the following preparation steps must be performed:</br>

各テストでは、以下の準備ステップを実行する必要があります:</br>。

1. Clear database
2. Prepare mocks
3. Initialize testing module

4. データベースのクリア
5. モックの準備
6. テストモジュールの初期化

```csharp
[SetUp]
public async Task BeforeEachTest()
{
    const string connectionStringEnvironmentVariable =
        "ASPNETCORE_MyMeetings_IntegrationTests_ConnectionString";
    ConnectionString = Environment.GetEnvironmentVariable(connectionStringEnvironmentVariable, EnvironmentVariableTarget.Machine);
    if (ConnectionString == null)
    {
        throw new ApplicationException(
            $"Define connection string to integration tests database using environment variable: {connectionStringEnvironmentVariable}");
    }

    using (var sqlConnection = new SqlConnection(ConnectionString))
    {
        await ClearDatabase(sqlConnection);
    }

    Logger = Substitute.For<ILogger>();
    EmailSender = Substitute.For<IEmailSender>();
    EventsBus = new EventsBusMock();
    ExecutionContext = new ExecutionContextMock(Guid.NewGuid());

    PaymentsStartup.Initialize(
        ConnectionString,
        ExecutionContext,
        Logger,
        EventsBus,
        false);

    PaymentsModule = new PaymentsModule();
}
```

After preparation, test is performed on clear database. Usually, it is the execution of some (or many) Commands and: </br>
a) running a Query or/and </br>
b) verifying mocks </br>
to check the result.

準備後、クリアなデータベースでテストを行う。通常は、いくつかの（または多くの）コマンドを実行し、次のようなことを行います。

a) クエリの実行 または/および </br>。
b) モックの検証 </br>。
を実行して結果を確認します。

```csharp
[TestFixture]
public class MeetingPaymentTests : TestBase
{
    [Test]
    public async Task CreateMeetingPayment_Test()
    {
        PayerId payerId = new PayerId(Guid.NewGuid());
        MeetingId meetingId = new MeetingId(Guid.NewGuid());
        decimal value = 100;
        string currency = "EUR";
        await PaymentsModule.ExecuteCommandAsync(new CreateMeetingPaymentCommand(Guid.NewGuid(),
            payerId, meetingId, value, currency));

        var payment = await PaymentsModule.ExecuteQueryAsync(new GetMeetingPaymentQuery(meetingId.Value, payerId.Value));

        Assert.That(payment.PayerId, Is.EqualTo(payerId.Value));
        Assert.That(payment.MeetingId, Is.EqualTo(meetingId.Value));
        Assert.That(payment.FeeValue, Is.EqualTo(value));
        Assert.That(payment.FeeCurrency, Is.EqualTo(currency));
    }
}
```

Each Command/Query processing is a separate execution (with different object graph resolution, context, database connection etc.) thanks to Composition Root of each module. This behavior is important and desirable.

各モジュールのコンポジションルートのおかげで、それぞれのコマンド/クエリ処理は、（オブジェクトグラフの解像度、コンテキスト、データベース接続などが異なる）独立した実行となります。この動作は重要であり、望ましいものです。

### 3.14 System Integration Testing

### 3.14 システム統合テスト

#### Definition

#### 定義

[System Integration Testing (SIT)](https://en.wikipedia.org/wiki/System_integration_testing) is performed to verify the interactions between the modules of a software system. It involves the overall testing of a complete system of many subsystem components or elements.

[システム統合テスト（SIT）](https://en.wikipedia.org/wiki/System_integration_testing)は、ソフトウェアシステムのモジュール間の相互作用を検証するために実施される。多くのサブシステムのコンポーネントや要素からなる完全なシステムの全体的なテストを行うことを含む。

#### Implementation

#### 実装

Implementation of system integration tests is based on approach of integration testing of modules in isolation (invoking commands and queries) described in the previous section.

システム統合テストの実施は、前節で説明した、モジュールを分離して統合テストを行う（コマンドやクエリを呼び出す）アプローチに基づいています。

The problem is that in this case we are dealing with **asynchronous communication**. Due to asynchrony, our **test must wait for the result** at certain times.

問題は、この場合、**非同期通信**を扱っていることです。非同期性のために、我々の**テストはある時間に結果を待たなければなりません**。

To correctly implement such tests, the **Sampling** technique and implementation described in the [Growing Object-Oriented Software, Guided by Tests](https://www.amazon.com/Growing-Object-Oriented-Software-Guided-Tests/dp/0321503627) book was used:

このようなテストを正しく実装するために、[Growing Object-Oriented Software, Guided by Tests](https://www.amazon.com/Growing-Object-Oriented-Software-Guided-Tests/dp/0321503627)という本で紹介されている**Sampling**という技術と実装を使用しています。

> An asynchronous test must wait for success and use timeouts to detect failure. This implies that every tested activity must have an observable effect: a test must affect the system so that its observable state becomes different. This sounds obvious but it drives how we think about writing asynchronous tests. If an activity has no observable effect, there is nothing the test can wait for, and therefore no way for the test to synchronize with the system it is testing. There are two ways a test can observe the system: by sampling its observable state or by listening for events that it sends out.

> 非同期テストでは、成功を待ち、失敗を検出するためにタイムアウトを使用する必要があります。これは、テストされたすべての活動が観測可能な効果を持っていなければならないことを意味しています。これは当たり前のことのように聞こえますが、非同期テストを書く際の考え方の指針となります。もしアクティビティに観測可能な効果がなければ、テストは何も待つことができず、したがってテストしているシステムと同期する方法がありません。テストがシステムを観察するには 2 つの方法があります。観察可能な状態をサンプリングする方法と、システムが発信するイベントをリスニングする方法です。

![](docs/Images/SystemIntegrationTests.jpg)

Test below:

下のテストです。

1. Creates Meeting Group Proposal in Meetings module
2. Waits until Meeting Group Proposal to verification will be available in Administration module with 10 seconds timeout
3. Accepts Meeting Group Proposal in Administration module
4. Waits until Meeting Group is created in Meetings module with 15 seconds timeout

5. Meetings モジュールで Meeting Group Proposal を作成します。
6. 検証用の会議グループ案が Administration モジュールで利用できるようになるまで、10 秒のタイムアウトで待ちます。
7. 3. 管理画面で会議グループの提案を承認する
8. ミーティングモジュールでミーティンググループが作成されるまで、15 秒のタイムアウトで待ちます。

```csharp
public class CreateMeetingGroupTests : TestBase
{
    [Test]
    public async Task CreateMeetingGroupScenario_WhenProposalIsAccepted()
    {
        var meetingGroupId = await MeetingsModule.ExecuteCommandAsync(
            new ProposeMeetingGroupCommand("Name",
            "Description",
            "Location",
            "PL"));

        AssertEventually(
            new GetMeetingGroupProposalFromAdministrationProbe(meetingGroupId, AdministrationModule),
            10000);

        await AdministrationModule.ExecuteCommandAsync(new AcceptMeetingGroupProposalCommand(meetingGroupId));

        AssertEventually(
            new GetCreatedMeetingGroupFromMeetingsProbe(meetingGroupId, MeetingsModule),
            15000);
    }

    private class GetCreatedMeetingGroupFromMeetingsProbe : IProbe
    {
        private readonly Guid _expectedMeetingGroupId;

        private readonly IMeetingsModule _meetingsModule;

        private List<MeetingGroupDto> _allMeetingGroups;

        public GetCreatedMeetingGroupFromMeetingsProbe(
            Guid expectedMeetingGroupId,
            IMeetingsModule meetingsModule)
        {
            _expectedMeetingGroupId = expectedMeetingGroupId;
            _meetingsModule = meetingsModule;
        }

        public bool IsSatisfied()
        {
            return _allMeetingGroups != null &&
                   _allMeetingGroups.Any(x => x.Id == _expectedMeetingGroupId);
        }

        public async Task SampleAsync()
        {
            _allMeetingGroups = await _meetingsModule.ExecuteQueryAsync(new GetAllMeetingGroupsQuery());
        }

        public string DescribeFailureTo()
            => $"Meeting group with ID: {_expectedMeetingGroupId} is not created";
    }

    private class GetMeetingGroupProposalFromAdministrationProbe : IProbe
    {
        private readonly Guid _expectedMeetingGroupProposalId;

        private MeetingGroupProposalDto _meetingGroupProposal;

        private readonly IAdministrationModule _administrationModule;

        public GetMeetingGroupProposalFromAdministrationProbe(Guid expectedMeetingGroupProposalId, IAdministrationModule administrationModule)
        {
            _expectedMeetingGroupProposalId = expectedMeetingGroupProposalId;
            _administrationModule = administrationModule;
        }

        public bool IsSatisfied()
        {
            if (_meetingGroupProposal == null)
            {
                return false;
            }

            if (_meetingGroupProposal.Id == _expectedMeetingGroupProposalId &&
                _meetingGroupProposal.StatusCode == MeetingGroupProposalStatus.ToVerify.Value)
            {
                return true;
            }

            return false;
        }

        public async Task SampleAsync()
        {
            try
            {
                _meetingGroupProposal =
                    await _administrationModule.ExecuteQueryAsync(
                        new GetMeetingGroupProposalQuery(_expectedMeetingGroupProposalId));
            }
            catch
            {
                // ignored
            }
        }

        public string DescribeFailureTo()
            => $"Meeting group proposal with ID: {_expectedMeetingGroupProposalId} to verification not created";
    }
}
```

Poller class implementation (based on example in the book):

```csharp
public class Poller
{
    private readonly int _timeoutMillis;

    private readonly int _pollDelayMillis;

    public Poller(int timeoutMillis)
    {
        _timeoutMillis = timeoutMillis;
        _pollDelayMillis = 1000;
    }

    public void Check(IProbe probe)
    {
        var timeout = new Timeout(_timeoutMillis);
        while (!probe.IsSatisfied())
        {
            if (timeout.HasTimedOut())
            {
                throw new AssertErrorException(DescribeFailureOf(probe));
            }

            Thread.Sleep(_pollDelayMillis);
            probe.SampleAsync();
        }
    }

    private static string DescribeFailureOf(IProbe probe)
    {
        return probe.DescribeFailureTo();
    }
}
```

### 3.15 Event Sourcing

#### Theory

#### 理論

During the implementation of the Payment module, _Event Sourcing_ was used. _Event Sourcing_ is a way of preserving the state of our system by recording a sequence of events. No less, no more.

Payment モジュールの実装では、_Event Sourcing_ を使用しました。イベントソーシングは、一連のイベントを記録することで、システムの状態を保持する方法です。それ以下でもそれ以上でもありません。

It is important here to really restore the state of our application from events. If we collect events only for auditing purposes, it is an [Audit Log/Trail](https://en.wikipedia.org/wiki/Audit_trail) - not the _Event Sourcing_.

ここで重要なのは、イベントからアプリケーションの状態を本当に復元することです。監査目的でのみイベントを収集する場合、それは[Audit Log/Trail](https://en.wikipedia.org/wiki/Audit_trail)であり、*Event Sourcing*ではありません。

The main elements of _Event Sourcing_ are as follows:

Event Sourcing\_の主な要素は以下のとおりです。

- Events Stream
- Objects that are restored based on events. There are 2 types of such objects depending on the purpose:
  -- Objects responsible for the change of state. In Domain-Driven Design they will be _Aggregates_.
  -- _Projections_: read models prepared for a specific purpose
- _Subscriptions_ : a way to receive information about new events
- _Snapshots_: from time to time, objects saved in the traditional way for performance purposes. Mainly used if there are many events to restore the object from the entire event history. (Note: there is currently no snapshot implementation in the project)

- イベントストリーム
- イベントに基づいて復元されるオブジェクト。このようなオブジェクトには、目的に応じて 2 つのタイプがあります。
  -- 状態の変化に責任を持つオブジェクト。ドメイン駆動設計では、これらは _Aggregates_ になります。
  -- _Projections_: 特定の目的のために用意されたモデルを読む。
- _Subscriptions_: 新しいイベントの情報を受け取る方法
- _Snapshots_: 時々、パフォーマンス目的で従来の方法で保存されるオブジェクト。主に、イベント履歴全体からオブジェクトを復元するために、多くのイベントがある場合に使用されます。(注：現在、プロジェクトにはスナップショットの実装はありません)

![](docs/Images/ES_elements.jpg)

#### Tool

#### ツール

In order not to reinvent the wheel, the _SQL Stream Store_ library was used. As the [documentation](https://sqlstreamstore.readthedocs.io/en/latest/) says:

車輪の再発明をしないために、*SQL Stream Store*ライブラリを使用しました。ドキュメント](https://sqlstreamstore.readthedocs.io/en/latest/)にある通りです。

_SQL Stream Store is a .NET library to assist with developing applications that use event sourcing or wish to use stream based patterns over a relational database and existing operational infrastructure._

SQL Stream Store は、イベントソーシングを使用するアプリケーションや、リレーショナルデータベースと既存の運用インフラ上でストリームベースのパターンを使用したいアプリケーションの開発を支援する.NET ライブラリです。

Like every library, it has its limitations and assumptions (I recommend the linked documentation chapter "Things you need to know before adopting"). For me, the most important 2 points from this chapter are:

他のライブラリと同様に、このライブラリにも制限や前提条件があります（リンク先のドキュメントの「採用する前に知っておくべきこと」の章をお勧めします）。私にとって、この章で最も重要なのは次の 2 点です。

1. _"Subscriptions (and thus projections) are **eventually consistent** and always will be."_ This means that there will always be an inconsistency time from saving the event to the stream and processing the event by the projector(s).
2. _"No support for ambient System.Transaction scopes enforcing the concept of the stream as the consistency and transactional boundary."_ This means that if we save the event to a events stream and want to save something **in the same transaction**, we must use [TransactionScope](https://docs.microsoft.com/en-us/dotnet/api/system.transactions.transactionscope?view=netcore-3.1). If we cannot use _TransactionScope_ for some reason, we must accept the Eventual Consistency also in this case.

3. これは、イベントをストリームに保存してから、プロジェクタでイベントを処理するまでの時間には、常に不整合があるということです。
4. 2. "No support for ambient System.Transaction scopes enforcing the concept of the stream as the consistency and transactional boundary." * これは、イベントをイベントストリームに保存し、同じトランザクションで\*\*何かを保存したい場合、[TransactionScope](https://docs.microsoft.com/en-us/dotnet/api/system.transactions.transactionscope?view=netcore-3.1)を使用しなければならないことを意味しています。もし、何らかの理由で\_TransactionScope*が使えない場合は、この場合も Eventual Consistency を受け入れなければなりません。

Other popular tools:

他にも有名なツールがあります。

- [EventStore](https://eventstore.com/) _"An industrial-strength database solution built from the ground up for event sourcing."_
- [Marten](https://martendb.io/) _".NET Transactional Document DB and Event Store on PostgreSQL"_

- EventStore](https://eventstore.com/) \_"An industrial-strength database solution built from the ground up for event sourcing."（イベントソーシングのためにゼロから構築された強力なデータベースソリューション）。
- [Marten](https://martendb.io/) _"PostgreSQL 上の.NET トランザクションドキュメント DB とイベントストア"_。

#### Implementation

#### 実装

There are 2 main "flows" to handle:

処理する主な「流れ」は 2 つあります。

- Command handling: change of state - adding new events to stream (writing)
- Projection of events to create read models

- コマンド処理：状態の変化 - ストリームへの新しいイベントの追加(書き込み)
- 読み取りモデルを作成するためのイベントのプロジェクション

##### Command Handling

##### コマンド処理

The whole process looks like this:

全体の流れは次のようになっています。

![](docs/Images/ES_command_handling.png)

1. We create / update an aggregate by creating an event
2. We add changes to the Aggregate Store. This is the class responsible for writing / loading our aggregates. We are not saving changes yet.
3. As part of Unit Of Work a) Aggregate Store adds events to the stream b) messages are added to the Outbox

4. イベントを作成することで、アグリゲートの作成/更新を行う
5. 2. アグリゲートストアに変更を追加する。これは、アグリゲートの書き込み/読み込みを行うクラスです。まだ変更を保存していません。
6. 3. Unit Of Work の一環として a) Aggregate Store がイベントをストリームに追加する b) メッセージが Outbox に追加される

Command Handler:

```csharp
public class BuySubscriptionCommandHandler : ICommandHandler<BuySubscriptionCommand, Guid>
{
    private readonly IAggregateStore _aggregateStore;

    private readonly IPayerContext _payerContext;

    private readonly ISqlConnectionFactory _sqlConnectionFactory;

    public BuySubscriptionCommandHandler(
        IAggregateStore aggregateStore,
        IPayerContext payerContext,
        ISqlConnectionFactory sqlConnectionFactory)
    {
        _aggregateStore = aggregateStore;
        _payerContext = payerContext;
        _sqlConnectionFactory = sqlConnectionFactory;
    }

    public async Task<Guid> Handle(BuySubscriptionCommand command, CancellationToken cancellationToken)
    {
        var priceList = await PriceListProvider.GetPriceList(_sqlConnectionFactory.GetOpenConnection());

        var subscriptionPayment = SubscriptionPayment.Buy(
            _payerContext.PayerId,
            SubscriptionPeriod.Of(command.SubscriptionTypeCode),
            command.CountryCode,
            MoneyValue.Of(command.Value, command.Currency),
            priceList);

        _aggregateStore.AppendChanges(subscriptionPayment);

        return subscriptionPayment.Id;
    }
}
```

`SubscriptionPayment` Aggregate:

```csharp
public class SubscriptionPayment : AggregateRoot
{
    private PayerId _payerId;

    private SubscriptionPeriod _subscriptionPeriod;

    private string _countryCode;

    private SubscriptionPaymentStatus _subscriptionPaymentStatus;

    private MoneyValue _value;

    protected override void Apply(IDomainEvent @event)
    {
        this.When((dynamic)@event);
    }

    public static SubscriptionPayment Buy(
        PayerId payerId,
        SubscriptionPeriod period,
        string countryCode,
        MoneyValue priceOffer,
        PriceList priceList)
    {
        var priceInPriceList = priceList.GetPrice(countryCode, period, PriceListItemCategory.New);
        CheckRule(new PriceOfferMustMatchPriceInPriceListRule(priceOffer, priceInPriceList));

        var subscriptionPayment = new SubscriptionPayment();

        var subscriptionPaymentCreated = new SubscriptionPaymentCreatedDomainEvent(
            Guid.NewGuid(),
            payerId.Value,
            period.Code,
            countryCode,
            SubscriptionPaymentStatus.WaitingForPayment.Code,
            priceOffer.Value,
            priceOffer.Currency);

        subscriptionPayment.Apply(subscriptionPaymentCreated);
        subscriptionPayment.AddDomainEvent(subscriptionPaymentCreated);

        return subscriptionPayment;
    }

    private void When(SubscriptionPaymentCreatedDomainEvent @event)
    {
        this.Id = @event.SubscriptionPaymentId;
        _payerId = new PayerId(@event.PayerId);
        _subscriptionPeriod = SubscriptionPeriod.Of(@event.SubscriptionPeriodCode);
        _countryCode = @event.CountryCode;
        _subscriptionPaymentStatus = SubscriptionPaymentStatus.Of(@event.Status);
        _value = MoneyValue.Of(@event.Value, @event.Currency);
    }
```

`AggregateRoot` base class:

```csharp
public abstract class AggregateRoot
{
    public Guid Id { get; protected set; }

    public int Version { get; private set; }

    private readonly List<IDomainEvent> _domainEvents;

    protected AggregateRoot()
    {
        _domainEvents = new List<IDomainEvent>();

        Version = -1;
    }

    protected void AddDomainEvent(IDomainEvent @event)
    {
        _domainEvents.Add(@event);
    }

    public IReadOnlyCollection<IDomainEvent> GetDomainEvents() => _domainEvents.AsReadOnly();

    public void Load(IEnumerable<IDomainEvent> history)
    {
        foreach (var e in history)
        {
            Apply(e);
            Version++;
        }
    }

    protected abstract void Apply(IDomainEvent @event);

    protected static void CheckRule(IBusinessRule rule)
    {
        if (rule.IsBroken())
        {
            throw new BusinessRuleValidationException(rule);
        }
    }
}

```

Aggregate Store implementation with SQL Stream Store library usage:

```csharp
public class SqlStreamAggregateStore : IAggregateStore
{
    private readonly IStreamStore _streamStore;

    private readonly List<IDomainEvent> _appendedChanges;

    private readonly List<AggregateToSave> _aggregatesToSave;

    public SqlStreamAggregateStore(
        ISqlConnectionFactory sqlConnectionFactory)
    {
        _appendedChanges = new List<IDomainEvent>();

        _streamStore =
            new MsSqlStreamStore(
                new MsSqlStreamStoreSettings(sqlConnectionFactory.GetConnectionString())
                    {
                        Schema = DatabaseSchema.Name
                });

        _aggregatesToSave = new List<AggregateToSave>();
    }

    public async Task Save()
    {
        foreach (var aggregateToSave in _aggregatesToSave)
        {
            await _streamStore.AppendToStream(
                GetStreamId(aggregateToSave.Aggregate),
                aggregateToSave.Aggregate.Version,
                aggregateToSave.Messages.ToArray());
        }

        _aggregatesToSave.Clear();
    }

    public async Task<T> Load<T>(AggregateId<T> aggregateId) where T : AggregateRoot
    {
        var streamId = GetStreamId(aggregateId);

        IList<IDomainEvent> domainEvents = new List<IDomainEvent>();
        ReadStreamPage readStreamPage;
        do
        {
            readStreamPage = await _streamStore.ReadStreamForwards(streamId, StreamVersion.Start, maxCount: 100);
            var messages = readStreamPage.Messages;
            foreach (var streamMessage in messages)
            {
                Type type = DomainEventTypeMappings.Dictionary[streamMessage.Type];
                var jsonData = await streamMessage.GetJsonData();
                var domainEvent = JsonConvert.DeserializeObject(jsonData, type) as IDomainEvent;

                domainEvents.Add(domainEvent);
            }
        } while (!readStreamPage.IsEnd);

        var aggregate = (T)Activator.CreateInstance(typeof(T), true);

        aggregate.Load(domainEvents);

        return aggregate;
    }

```

##### Events Projection

##### イベント映写

The whole process looks like this:

全体の流れはこのようになっています。

![](docs/Images/ES_events_projection.png)

1. Special class `Subscriptions Manager` subscribes to Events Store (using SQL Store Stream library)
2. Events Store raises `StreamMessageRecievedEvent`
3. `Subscriptions Manager` invokes all projectors
4. If projector know how to handle given event, it updates particular read model. In current implementation it updates special table in SQL database.

5. 特別なクラス `Subscriptions Manager` がイベントストアを購読する (SQL Store Stream ライブラリを使用)
6. イベントストアが `StreamMessageRecievedEvent` を発生させる
7. 3. `サブスクリプションマネージャ` がすべてのプロジェクタを起動する。
8. 4. プロジェクターが与えられたイベントの処理方法を知っている場合は、特定のリードモデルを更新する。現在の実装では、SQL データベースの特別なテーブルを更新します。

`SubscriptionsManager` class implementation:

```csharp
public class SubscriptionsManager
{
    private readonly IStreamStore _streamStore;

    public SubscriptionsManager(
        IStreamStore streamStore)
    {
        _streamStore = streamStore;
    }

    public void Start()
    {
        long? actualPosition;

        using (var scope = PaymentsCompositionRoot.BeginLifetimeScope())
        {
            var checkpointStore = scope.Resolve<ICheckpointStore>();

            actualPosition = checkpointStore.GetCheckpoint(SubscriptionCode.All);
        }

        _streamStore.SubscribeToAll(actualPosition, StreamMessageReceived);
    }

    public void Stop()
    {
        _streamStore.Dispose();
    }

    private static async Task StreamMessageReceived(
        IAllStreamSubscription subscription, StreamMessage streamMessage, CancellationToken cancellationToken)
    {
        var type = DomainEventTypeMappings.Dictionary[streamMessage.Type];
        var jsonData = await streamMessage.GetJsonData(cancellationToken);
        var domainEvent = JsonConvert.DeserializeObject(jsonData, type) as IDomainEvent;

        using var scope = PaymentsCompositionRoot.BeginLifetimeScope();

        var projectors = scope.Resolve<IList<IProjector>>();

        var tasks = projectors
            .Select(async projector =>
            {
                await projector.Project(domainEvent);
            });

        await Task.WhenAll(tasks);

        var checkpointStore = scope.Resolve<ICheckpointStore>();
        await checkpointStore.StoreCheckpoint(SubscriptionCode.All, streamMessage.Position);
    }
}

```

Example projector:

```csharp
internal class SubscriptionDetailsProjector : ProjectorBase, IProjector
{
    private readonly IDbConnection _connection;

    public SubscriptionDetailsProjector(ISqlConnectionFactory sqlConnectionFactory)
    {
        _connection = sqlConnectionFactory.GetOpenConnection();
    }

    public async Task Project(IDomainEvent @event)
    {
        await When((dynamic) @event);
    }

    private async Task When(SubscriptionRenewedDomainEvent subscriptionRenewed)
    {
        var period = SubscriptionPeriod.GetName(subscriptionRenewed.SubscriptionPeriodCode);

        await _connection.ExecuteScalarAsync("UPDATE payments.SubscriptionDetails " +
                                                "SET " +
                                                    "[Status] = @Status, " +
                                                    "[ExpirationDate] = @ExpirationDate, " +
                                                    "[Period] = @Period " +
                                                "WHERE [Id] = @SubscriptionId",
            new
            {
                subscriptionRenewed.SubscriptionId,
                subscriptionRenewed.Status,
                subscriptionRenewed.ExpirationDate,
                period
            });
    }

    private async Task When(SubscriptionExpiredDomainEvent subscriptionExpired)
    {
        await _connection.ExecuteScalarAsync("UPDATE payments.SubscriptionDetails " +
                                             "SET " +
                                             "[Status] = @Status " +
                                             "WHERE [Id] = @SubscriptionId",
            new
            {
                subscriptionExpired.SubscriptionId,
                subscriptionExpired.Status
            });
    }

    private async Task When(SubscriptionCreatedDomainEvent subscriptionCreated)
    {
        var period = SubscriptionPeriod.GetName(subscriptionCreated.SubscriptionPeriodCode);

        await _connection.ExecuteScalarAsync("INSERT INTO payments.SubscriptionDetails " +
                                       "([Id], [Period], [Status], [CountryCode], [ExpirationDate]) " +
                                       "VALUES (@SubscriptionId, @Period, @Status, @CountryCode, @ExpirationDate)",
            new
            {
                subscriptionCreated.SubscriptionId,
                period,
                subscriptionCreated.Status,
                subscriptionCreated.CountryCode,
                subscriptionCreated.ExpirationDate
            });
    }
}

```

#### Sample view of Event Store

#### イベントストアのサンプルビュー

Sample _Event Store_ view after execution of SubscriptionLifecycleTests Integration Test which includes following steps:

以下のステップを含む SubscriptionLifecycleTests Integration Test を実行した後の _Event Store_ ビューのサンプルです。

1. Creating Price List
2. Buying Subscription
3. Renewing Subscription
4. Expiring Subscription

5. 価格表の作成
6. サブスクリプションの購入
7. 月額プランの更新
8. 購読期間の終了

looks like this (_SQL Stream Store_ table - _payments.Messages_):

は次のようになります（*SQL Stream Store*テーブル - _payments.Messages_）。

![](docs/Images/ES_event_store_db_sample.png)

### 3.16 Database Change Management

### 3.16 データベースの変更管理

Database change management is accomplished by _migrations/transitions_ versioning. Additionally, the current state of the database structure is also versioned.

データベースの変更管理は、_migrations/transitions_ バージョニングによって実現されます。また、データベース構造の現在の状態もバージョン管理されます。

Migrations are applied using a simple [DatabaseMigrator](src/Database/DatabaseMigrator) console application that uses the [DbUp](https://dbup.readthedocs.io/en/latest/) library. The current state of the database structure is kept in the [SSDT Database Project](https://docs.microsoft.com/en-us/sql/ssdt/how-to-create-a-new-database-project).

移行は、[DbUp](https://dbup.readthedocs.io/en/latest/)ライブラリを使用したシンプルな [DatabaseMigrator](src/Database/DatabaseMigrator)コンソールアプリケーションで行います。データベース構造の現在の状態は、[SSDT Database Project](https://docs.microsoft.com/en-us/sql/ssdt/how-to-create-a-new-database-project)に保持されています。

The database update is performed by running the following command:

データベースの更新は，以下のコマンドを実行することで行います．

```shell
dotnet DatabaseMigrator.dll "connection_string" "scripts_directory_path"
```

The entire solution is described in detail in the following articles:

このソリューション全体については、以下の記事で詳しく説明しています。

1. [Database change management](https://www.kamilgrzybek.com/database/database-change-management/) (theory)
2. [Using database project and DbUp for database management](https://www.kamilgrzybek.com/database/using-database-project-and-dbup-for-database-management/) (implementation)

### 3.17 Continuous Integration

### 3.17 継続的インテグレーション

#### Definition

#### 定義

As defined on [Martin Fowler's website](https://martinfowler.com/articles/continuousIntegration.html):

Martin Fowler 氏のウェブサイト](https://martinfowler.com/articles/continuousIntegration.html)で定義されています。

> _Continuous Integration is a software development practice where members of a team integrate their work frequently, usually each person integrates at least daily - leading to multiple integrations per day. Each integration is verified by an automated build (including test) to detect integration errors as quickly as possible._

> 継続的インテグレーションとは、チームのメンバーが自分の作業を頻繁に統合するソフトウェア開発手法です。各統合は自動ビルド（テストを含む）によって検証され、統合エラーを可能な限り迅速に検出します。

#### YAML Implementation [OBSOLETE]

#### YAML の実装 [OBSOLETE]（英語

_Originally the build was implemented using yaml and GitHub Actions functionality. Currently, the build is implemented with NUKE (see next section). See [buildPipeline.yml](.github/workflows/buildPipeline.yml)_ file history.

*当初、ビルドは yaml と GitHub Actions 機能を使って実装されていました。現在は、NUKE を使ってビルドを実装しています（次項参照）。[buildPipeline.yml](.github/workflows/buildPipeline.yml)*のファイル履歴をご覧ください。

##### Pipeline description

##### パイプラインの説明

CI was implemented using [GitHub Actions](https://docs.github.com/en/actions/getting-started-with-github-actions/about-github-actions). For this purpose, one workflow, which triggers on Pull Request to _master_ branch or Push to _master_ branch was created. It contains 2 jobs:

CI は[GitHub Actions](https://docs.github.com/en/actions/getting-started-with-github-actions/about-github-actions)を使って実装しました。この目的のために、*master*ブランチへの Pull Request または*master*ブランチへの Push をトリガーとする 1 つのワークフローを作成しました。このワークフローには 2 つのジョブがあります。

- build test, execute Unit Tests and Architecture Tests
- execute Integration Tests

- テストの構築、ユニットテストとアーキテクチャテストの実行
- 統合テストの実行

![](docs/Images/ci.jpg)

**Steps description**<br/>
a) Checkout repository - clean checkout of git repository <br/>
b) Setup .NET Core - install .NET Core SDK<br/>
c) Install dependencies - resolve NuGet packages<br/>
d) Build - build solution<br/>
e) Run Unit Tests - run automated Unit Tests (see section 3.10)<br/>
f) Run Architecture Tests - run automated Architecture Tests (see section 3.12)<br/>
g) Initialize containers - setup Docker container for MS SQL Server<br/>
h) Wait for SQL Server initialization - after container initialization MS SQL Server is not ready, initialization of server itself takes some time so 30 seconds timeout before execution of next step is needed<br/>
i) Create Database - create and initialize database<br/>
j) Migrate Database - execute database upgrade using _DatabaseMigrator_ application (see 3.16 section)<br/>
k) Run Integration Tests - perform Integration and System Integration Testing (see section 3.13 and 3.14)<br/>

a) Checkout repository - git リポジトリのクリーンチェックアウト <br/>。
b) .NET Core のセットアップ - .NET Core SDK のインストール<br/>。
c) Install dependencies - NuGet パッケージを解決する<br/> <br/>
d) Build - ソリューションの構築<br/>。
e) Run Unit Tests - 自動化されたユニットテストを実行する（3.10 項参照）<br/>。
f) Run Architecture Tests - 自動化されたアーキテクチャテストを実行する（3.12 項参照）<br/>。
g) Initialize containers - MS SQL Server 用の Docker コンテナをセットアップする<br/>。
h) SQL Server の初期化を待つ - コンテナの初期化後、MS SQL Server の準備ができていません。サーバー自体の初期化には時間がかかるため、次のステップを実行する前に 30 秒のタイムアウトが必要です。
i) データベースの作成 - データベースの作成と初期化<br/>。
j) Migrate Database - _DatabaseMigrator_ アプリケーションを使ってデータベースのアップグレードを実行する（3.16 節参照）<br/>。
k) Run Integration Tests - 統合テストとシステム統合テストを実行する（3.13 と 3.14 節参照）<br/>。

##### Workflow definition

Workflow definition: [buildPipeline.yml](.github/workflows/buildPipeline.yml)

##### Example workflow execution

Example workflow output:

![](docs/Images/ci_job1.png)

![](docs/Images/ci_job2.png)

#### NUKE

[Nuke](https://nuke.build/) is _the cross-platform build automation solution for .NET with C# DSL._

[Nuke](https://nuke.build/)は、C# DSL を備えた.NET 用のクロスプラットフォームのビルド自動化ソリューションです。

The 2 main advantages of its use over pure yaml defined in GitHub actions are as follows:

GitHub アクションで定義された純粋な yaml と比較して、NUKE を使用する主な利点は以下の 2 つです。

- You run the same code on local machine and in the build server. See [buildPipeline.yml](.github/workflows/buildPipeline.yml)
- You use C# with all the goodness (debugging, compilation, packages, refactoring and so on)

- ローカルマシンとビルドサーバーで同じコードを実行する。buildPipeline.yml](.github/workflows/buildPipeline.yml)を参照してください。
- C#を使って、あらゆる機能（デバッグ、コンパイル、パッケージ、リファクタリングなど）を利用する。

This is how one of the stage definition looks like (execute Build, Unit Tests, Architecture Tests) [Build.cs](build/Build.cs):

ステージ定義の 1 つはこんな感じです（ビルド、ユニットテスト、アーキテクチャテストを実行） [Build.cs](build/Build.cs)。

```csharp
partial class Build : NukeBuild
{
    /// Support plugins are available for:
    ///   - JetBrains ReSharper        https://nuke.build/resharper
    ///   - JetBrains Rider            https://nuke.build/rider
    ///   - Microsoft VisualStudio     https://nuke.build/visualstudio
    ///   - Microsoft VSCode           https://nuke.build/vscode

    public static int Main () => Execute<Build>(x => x.Compile);

    [Parameter("Configuration to build - Default is 'Debug' (local) or 'Release' (server)")]
    readonly Configuration Configuration = IsLocalBuild ? Configuration.Debug : Configuration.Release;

    [Solution] readonly Solution Solution;

    Target Clean => _ => _
        .Before(Restore)
        .Executes(() =>
        {
            EnsureCleanDirectory(WorkingDirectory);
        });

    Target Restore => _ => _
        .Executes(() =>
        {
            DotNetRestore(s => s
                .SetProjectFile(Solution));
        });

    Target Compile => _ => _
        .DependsOn(Restore)
        .Executes(() =>
        {
            DotNetBuild(s => s
                .SetProjectFile(Solution)
                .SetConfiguration(Configuration)
                .EnableNoRestore());
        });

    Target UnitTests => _ => _
        .DependsOn(Compile)
        .Executes(() =>
        {
            DotNetTest(s => s
                .SetProjectFile(Solution)
                .SetFilter("UnitTests")
                .SetConfiguration(Configuration)
                .EnableNoRestore()
                .EnableNoBuild());
        });

    Target ArchitectureTests => _ => _
        .DependsOn(UnitTests)
        .Executes(() =>
        {
            DotNetTest(s => s
                .SetProjectFile(Solution)
                .SetFilter("ArchTests")
                .SetConfiguration(Configuration)
                .EnableNoRestore()
                .EnableNoBuild());
        });

    Target BuildAndUnitTests => _ => _
        .Triggers(ArchitectureTests)
        .Executes(() =>
        {
        });
}

```

If you want to see more complex scenario when integration tests are executed (with SQL Server database creation using docker) see [BuildIntegrationTests.cs](build/BuildIntegrationTests.cs) file.

統合テスト実行時のより複雑なシナリオ（docker を使って SQL Server データベースを作成した場合）を見たい場合は、[BuildIntegrationTests.cs](build/BuildIntegrationTests.cs)ファイルを参照してください。

#### SQL Server database project build

#### SQL Server データベースプロジェクトのビルド

Currently, compilation of database projects is not supported by the .NET Core and dotnet tool. For this reason, the [MSBuild.Sdk.SqlProj](https://github.com/rr-wfm/MSBuild.Sdk.SqlProj/) library was used. In order to do that, you need to create .NET standard library, change SDK and create links to scripts folders. Final [database project](src/Database/CompanyName.MyMeetings.Database.Build/CompanyName.MyMeetings.Database.Build.csproj) looks as follows:

現在、データベースプロジェクトのコンパイルは、.NET Core および dotnet ツールではサポートされていません。このため、[MSBuild.Sdk.SqlProj](https://github.com/rr-wfm/MSBuild.Sdk.SqlProj/)のライブラリを使用しています。そのためには、.NET 標準ライブラリの作成、SDK の変更、scripts フォルダへのリンクの作成が必要です。最終的な[データベースプロジェクト](src/Database/CompanyName.MyMeetings.Database.Build/CompanyName.MyMeetings.Database.Build.csproj)は以下のようになります。

```xml
<Project Sdk="MSBuild.Sdk.SqlProj/1.6.0">
    <PropertyGroup>
        <TargetFramework>netstandard2.0</TargetFramework>
    </PropertyGroup>
    <ItemGroup>
        <Content Include="..\CompanyName.MyMeetings.Database\administration\**\*.sql" />
        <Content Include="..\CompanyName.MyMeetings.Database\app\**\*.sql" />
        <Content Include="..\CompanyName.MyMeetings.Database\meetings\**\*.sql" />
        <Content Include="..\CompanyName.MyMeetings.Database\payments\**\*.sql" />
        <Content Include="..\CompanyName.MyMeetings.Database\users\**\*.sql" />
        <Content Include="..\CompanyName.MyMeetings.Database\Security\**\*.sql" />
    </ItemGroup>
</Project>
```

### 3.18 Static code analysis

### 3.18 静的コード解析

In order to standardize the appearance of the code and increase its readability, the [StyleCopAnalyzers](https://github.com/DotNetAnalyzers/StyleCopAnalyzers) library was used. This library implements StyleCop rules using the .NET Compiler Platform and is responsible for the static code analysis.<br/>

コードの外観を標準化し、可読性を高めるために、[StyleCopAnalyzers](https://github.com/DotNetAnalyzers/StyleCopAnalyzers)というライブラリを使用しました。このライブラリは、.NET Compiler Platform を使用して StyleCop のルールを実装し、静的なコード解析を行います。

Using this library is trivial - it is just added as a NuGet package to all projects. There are many ways to configure rules, but currently the best way to do this is to edit the [.editorconfig](src/.editorconfig) file. More information can be found at the link above.<br/>

このライブラリを使用するのは簡単で、すべてのプロジェクトに NuGet パッケージとして追加するだけです。ルールを設定するには多くの方法がありますが、現在のところ、[.editorconfig](src/.editorconfig)ファイルを編集するのが最も良い方法です。詳細は上記のリンクを参照してください。<br/>。

**Note! Static code analysis works best when the following points are met:**<br/>

\*\*注意! 静的コード解析は、以下の点が満たされている場合に最も効果的です。

1. Each developer has an IDE that respects the rules and helps to follow them
2. The rules are checked during the project build process as part of Continuous Integration
3. The rules are set to _help your system grow_. **Static analysis is not a value in itself.** Some rules may not make complete sense and should be turned off. Other rules may have higher priority. It all depends on the project, company standards and people involved in the project. Be pragmatic.

4. 各開発者は、ルールを尊重し、ルールに従うことを支援する IDE を持っている。
5. 継続的インテグレーションの一環として、プロジェクトのビルドプロセスでルールがチェックされている。
6. ルールは、システムの成長を助けるために設定されています。**静的解析はそれ自体が価値ではありません。** いくつかのルールは完全には意味をなさないかもしれず、オフにしておくべきです。他のルールの方が優先順位が高いかもしれません。すべては、プロジェクト、会社の基準、プロジェクトに関わる人々によります。現実的であること。

## 4. Technology

List of technologies, frameworks and libraries used for implementation:

- [.NET Core 3.1](https://dotnet.microsoft.com/download) (platform). Note for Visual Studio users: **VS 2019** is required.
- [MS SQL Server Express](https://www.microsoft.com/en-us/sql-server/sql-server-editions-express) (database)
- [Entity Framework Core 3.1](https://docs.microsoft.com/en-us/ef/core/) (ORM Write Model implementation for DDD)
- [Autofac](https://autofac.org/) (Inversion of Control Container)
- [IdentityServer4](http://docs.identityserver.io) (Authentication and Authorization)
- [Serilog](https://serilog.net/) (structured logging)
- [Hellang.Middleware.ProblemDetails](https://github.com/khellang/Middleware/tree/master/src/ProblemDetails) (API Problem Details support)
- [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle) (Swagger automated documentation)
- [Dapper](https://github.com/StackExchange/Dapper) (micro ORM for Read Model)
- [Newtonsoft.Json](https://www.newtonsoft.com/json) (serialization/deserialization to/from JSON)
- [Quartz.NET](https://www.quartz-scheduler.net/) (background processing)
- [FluentValidation](https://fluentvalidation.net/) (data validation)
- [MediatR](https://github.com/jbogard/MediatR) (mediator implementation)
- [Postman](https://www.getpostman.com/) (API tests)
- [NUnit](https://nunit.org/) (Testing framework)
- [NSubstitute](https://nsubstitute.github.io/) (Testing isolation framework)
- [Visual Paradigm Community Edition](https://www.visual-paradigm.com/download/community.jsp) (CASE tool for modeling and documentation)
- [NetArchTest](https://github.com/BenMorris/NetArchTest) (Architecture Unit Tests library)
- [Polly](https://github.com/App-vNext/Polly) (Resilience and transient-fault-handling library)
- [SQL Stream Store](https://github.com/SQLStreamStore) (Library to assist with Event Sourcing)
- [DbUp](https://dbup.readthedocs.io/en/latest/) (Database migrations deployment)
- [SSDT Database Project](https://docs.microsoft.com/en-us/sql/ssdt/how-to-create-a-new-database-project) (Database structure versioning)
- [GitHub Actions](https://docs.github.com/en/actions) (Continuous Integration workflows implementation)
- [StyleCopAnalyzers](https://github.com/DotNetAnalyzers/StyleCopAnalyzers) (Static code analysis library)
- [PlantUML](https://plantuml.com) (UML diagrams from textual description, diagrams as text)
- [C4 Model](https://c4model.com/) (Model for visualising software architecture)
- [C4-PlantUML](https://github.com/plantuml-stdlib/C4-PlantUML) (C4 Model for PlantUML plugin)
- [NUKE](https://nuke.build/) (Build automation system)
- [MSBuild.Sdk.SqlProj](https://github.com/rr-wfm/MSBuild.Sdk.SqlProj/) (Database project compilation)

## 5. How to Run

### Install .NET Core 3.1

- Download and install .NET Core 3.1 SDK

### Create database

- Download and install MS SQL Server Express or other
- Create an empty database using [CreateDatabase_Windows.sql](src/Database/CompanyName.MyMeetings.Database/Scripts/CreateDatabase_Windows.sql) or [CreateDatabase_Linux.sql](src/Database/CompanyName.MyMeetings.Database/Scripts/CreateDatabase_Linux.sql). Script adds **app** schema which is needed for migrations journal table. Change database file path if needed.
- Build [DatabaseMigrator](src/Database/DatabaseMigrator) application
- run database migrations:

```shell
dotnet DatabaseMigrator.dll "connection_string" "scripts_directory_path"
```

_"connection_string"_ - connection string to your database <br/>
_"scripts_directory_path"_ - [path to migration scripts](src/Database/CompanyName.MyMeetings.Database/Scripts/Migrations)

### Seed database

- Execute [SeedDatabase.sql](src/Database/CompanyName.MyMeetings.Database/Scripts/SeedDatabase.sql) script
- 2 test users will be created - check the script for usernames and passwords

### Configure connection string

Set a database connection string called `MeetingsConnectionString` in the root of the API project's appsettings.json or use [Secrets](https://blogs.msdn.microsoft.com/mihansen/2017/09/10/managing-secrets-in-net-core-2-0-apps/)

Example config setting in appsettings.json for a database called `ModularMonolith`:

```json
{
  "MeetingsConnectionString": "Server=(localdb)\\mssqllocaldb;Database=ModularMonolith;Trusted_Connection=True;"
}
```

### Configure startup in IDE

- Set the Startup Item in your IDE to the API Project, not IIS Express

### Authenticate

- Once it is running you'll need a token to make API calls. This is done via OAuth2 [Resource Owner Password Grant Type](https://www.oauth.com/oauth2-servers/access-tokens/password-grant/). By default IdentityServer is configured with the following:
- `client_id = ro.client`
- `client_secret = secret` **(this is literally the value - not a statement that this value is secret!)**
- `scope = myMeetingsAPI openid profile`
- `grant_type = password`

Include the credentials of a test user created in the [SeedDatabase.sql](src/Database/CompanyName.MyMeetings.Database/Scripts/SeedDatabase.sql) script - for example:

- `username = testMember@mail.com`
- `password = testMemberPass`

**Example HTTP Request for an Access Token:**

```http
POST /connect/token HTTP/1.1
Host: localhost:5000

grant_type=password
&username=testMember@mail.com
&password=testMemberPass
&client_id=ro.client
&client_secret=secret
```

This will fetch an access token for this user to make authorized API requests using the HTTP request header `Authorization: Bearer <access_token>`

If you use a tool such as Postman to test your API, the token can be fetched and stored within the tool itself and appended to all API calls. Check your tool documentation for instructions.

### Run using Docker Compose

You can run whole application using [docker compose](https://docs.docker.com/compose/) from root folder:

```shell
docker-compose up
```

It will create following services: <br/>

- MS SQL Server Database
- Database Migrator
- Application

## 6. Contribution

This project is still under analysis and development. I assume its maintenance for a long time and I would appreciate your contribution to it. Please let me know by creating an Issue or Pull Request.

## 7. Roadmap

List of features/tasks/approaches to add:

| Name                               | Status    | Release date |
| ---------------------------------- | --------- | ------------ |
| Domain Model Unit Tests            | Completed | 2019-09-10   |
| Architecture Decision Log update   | Completed | 2019-11-09   |
| Integration automated tests        | Completed | 2020-02-24   |
| Migration to .NET Core 3.1         | Completed | 2020-03-04   |
| System Integration Testing         | Completed | 2020-03-28   |
| More advanced Payments module      | Completed | 2020-07-11   |
| Event Sourcing implementation      | Completed | 2020-07-11   |
| Database Change Management         | Completed | 2020-08-23   |
| Continuous Integration             | Completed | 2020-09-01   |
| StyleCop Static Code Analysis      | Completed | 2020-09-05   |
| FrontEnd SPA application           | Completed | 2020-11-08   |
| Docker support                     | Completed | 2020-11-26   |
| PlantUML Conceptual Model          | Completed | 2021-03-22   |
| C4 Model                           | Completed | 2021-03-29   |
| Meeting comments feature           | Completed | 2021-03-30   |
| NUKE build automation              | Completed | 2021-06-15   |
| Database project compilation on CI | Completed | 2021-06-15   |

NOTE: Please don't hesitate to suggest something else or a change to the existing code. All proposals will be considered.

## 8. Authors

Kamil Grzybek

Blog: [https://kamilgrzybek.com](https://kamilgrzybek.com)

Twitter: [https://twitter.com/kamgrzybek](https://twitter.com/kamgrzybek)

LinkedIn: [https://www.linkedin.com/in/kamilgrzybek/](https://www.linkedin.com/in/kamilgrzybek/)

GitHub: [https://github.com/kgrzybek](https://github.com/kgrzybek)

### 8.1 Main contributors

- [Andrei Ganichev](https://github.com/AndreiGanichev)

## 9. License

The project is under [MIT license](https://opensource.org/licenses/MIT).

## 10. Inspirations and Recommendations

### Modular Monolith

- ["Modular Monolith: A Primer"](https://www.kamilgrzybek.com/design/modular-monolith-primer/) Modular Monolith architecture article series, Kamil Grzybek
- ["Modular Monolith Architecture: One to rule them all"](https://www.youtube.com/watch?v=njDSXUWeik0) presentation, Kamil Grzybek
- ["Modular Monoliths"](https://www.youtube.com/watch?v=5OjqD-ow8GE) presentation, Simon Brown
- ["Majestic Modular Monoliths"](https://www.youtube.com/watch?v=BOvxJaklcr0) presentation, Axel Fontaine
- ["Building Better Monoliths – Modulithic Applications with Spring Boot"](https://speakerdeck.com/olivergierke/building-better-monoliths-modulithic-applications-with-spring-boot-cd16e6ec-d334-497d-b9f6-3f92d5db035a) slides, Oliver Drotbohm
- ["MonolithFirst"](https://martinfowler.com/bliki/MonolithFirst.html) article, Martin Fowler
- ["Pattern: Monolithic Architecture"](https://microservices.io/patterns/monolithic.html) pattern description, Chris Richardson

### Domain-Driven Design

- ["Domain-Driven Design: Tackling Complexity in the Heart of Software"](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215) book, Eric Evans
- ["Implementing Domain-Driven Design"](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577) book, Vaughn Vernon
- ["Domain-Driven Design Distilled"](https://www.amazon.com/dp/0134434420) book, Vaughn Vernon
- ["Patterns, Principles, and Practices of Domain-Driven Design"](https://www.amazon.com/Patterns-Principles-Practices-Domain-Driven-Design-ebook/dp/B00XLYUA0W) book, Scott Millett, Nick Tune
- ["Secure By Design"](https://www.amazon.com/Secure-Design-Daniel-Deogun/dp/1617294357) book, Daniel Deogun, Dan Bergh Johnsson, Daniel Sawano
- ["Hands-On Domain-Driven Design with .NET Core: Tackling complexity in the heart of software by putting DDD principles into practice"](https://www.amazon.com/Hands-Domain-Driven-Design-NET-ebook/dp/B07C5WSR9B) book, Alexey Zimarev
- ["Domain Modeling Made Functional: Tackle Software Complexity with Domain-Driven Design and F#"](https://www.amazon.com/Domain-Modeling-Made-Functional-Domain-Driven-ebook/dp/B07B44BPFB) book, Scott Wlaschin
- ["DDD by examples - library"](https://github.com/ddd-by-examples/library) GH repository, Jakub Pilimon, Bartłomiej Słota
- ["IDDD_Samples"](https://github.com/VaughnVernon/IDDD_Samples) GH repository, Vaughn Vernon
- ["IDDD_Samples_NET"](https://github.com/VaughnVernon/IDDD_Samples_NET) GH repository, Vaughn Vernon
- ["Awesome Domain-Driven Design"](https://github.com/heynickc/awesome-ddd) GH repository, Nick Chamberlain

### Application Architecture

- ["Patterns of Enterprise Application Architecture"](https://martinfowler.com/books/eaa.html) book, Martin Fowler
- ["Dependency Injection Principles, Practices, and Patterns"](https://www.manning.com/books/dependency-injection-principles-practices-patterns) book, Steven van Deursen, Mark Seemann
- ["Clean Architecture: A Craftsman's Guide to Software Structure and Design (Robert C. Martin Series"](https://www.amazon.com/Clean-Architecture-Craftsmans-Software-Structure/dp/0134494164) book, Robert C. Martin
- ["The Clean Architecture"](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html) article, Robert C. Martin
- ["The Onion Architecture"](https://jeffreypalermo.com/2008/07/the-onion-architecture-part-1/) article series, Jeffrey Palermo
- ["Hexagonal/Ports & Adapters Architecture"](https://web.archive.org/web/20180822100852/http://alistair.cockburn.us/Hexagonal+architecture) article, Alistair Cockburn
- ["DDD, Hexagonal, Onion, Clean, CQRS, … How I put it all together"](https://herbertograca.com/2017/11/16/explicit-architecture-01-ddd-hexagonal-onion-clean-cqrs-how-i-put-it-all-together/) article, Herberto Graca

### Software Architecture

- ["Software Architecture in Practice (3rd Edition)"](https://www.amazon.com/Software-Architecture-Practice-3rd-Engineering/dp/0321815734) book, Len Bass, Paul Clements, Rick Kazman
- ["Software Architecture for Developers Vol 1 & 2"](https://softwarearchitecturefordevelopers.com/) book, Simon Brown
- ["Just Enough Software Architecture: A Risk-Driven Approach"](https://www.amazon.com/Just-Enough-Software-Architecture-Risk-Driven/dp/0984618104) book, George H. Fairbanks
- ["Software Systems Architecture: Working With Stakeholders Using Viewpoints and Perspectives (2nd Edition)"](https://www.amazon.com/Software-Systems-Architecture-Stakeholders-Perspectives/dp/032171833X/) book, Nick Rozanski, Eóin Woods
- ["Design It!: From Programmer to Software Architect (The Pragmatic Programmers)"](https://www.amazon.com/Design-Programmer-Architect-Pragmatic-Programmers/dp/1680502093) book, Michael Keeling

### System Architecture

- ["Enterprise Integration Patterns : Designing, Building, and Deploying Messaging Solutions"](https://www.enterpriseintegrationpatterns.com/) book and catalogue, Gregor Hohpe, Bobby Woolf
- ["Designing Data-Intensive Applications: The Big Ideas Behind Reliable, Scalable, and Maintainable Systems "](https://www.amazon.com/Designing-Data-Intensive-Applications-Reliable-Maintainable/dp/1449373321) book, Martin Kleppman
- ["Building Evolutionary Architectures: Support Constant Change"](https://www.amazon.com/Building-Evolutionary-Architectures-Support-Constant/dp/1491986360) book, Neal Ford
- ["Building Microservices: Designing Fine-Grained Systems"](https://www.amazon.com/Building-Microservices-Designing-Fine-Grained-Systems/dp/1491950358) book, Sam Newman

### Design

- ["Refactoring: Improving the Design of Existing Code"](https://www.amazon.com/Refactoring-Improving-Design-Existing-Code/dp/0201485672) book, Martin Fowler, Kent Beck, John Brant, William Opdyke, Don Roberts
- ["Clean Code: A Handbook of Agile Software Craftsmanship"](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882) book, Robert C. Martin
- ["Agile Principles, Patterns, and Practices in C#"](https://www.amazon.com/Agile-Principles-Patterns-Practices-C/dp/0131857258) book, Robert C. Martin
- ["Applying UML and Patterns: An Introduction to Object-Oriented Analysis and Design and Iterative Development (3rd Edition)"](https://www.amazon.com/Applying-UML-Patterns-Introduction-Object-Oriented/dp/0131489062) book, Craig Larman
- ["Working Effectively with Legacy Code"](https://www.amazon.com/Working-Effectively-Legacy-Michael-Feathers/dp/0131177052) book, Michael Feathers
- ["Code Complete: A Practical Handbook of Software Construction, Second Edition"](https://www.amazon.com/Code-Complete-Practical-Handbook-Construction/dp/0735619670) book, Steve McConnell
- ["Design Patterns: Elements of Reusable Object-Oriented Software"](https://www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612) book, Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides

### Craftsmanship

- ["The Clean Coder: A Code of Conduct for Professional Programmers"](https://www.amazon.com/Clean-Coder-Conduct-Professional-Programmers/dp/0137081073) book, Robert C. Martin
- ["The Pragmatic Programmer: From Journeyman to Master"](https://www.amazon.com/Pragmatic-Programmer-Journeyman-Master/dp/020161622X) book, Andrew Hunt

### Testing

- ["The Art of Unit Testing: with examples in C#"](https://www.amazon.com/Art-Unit-Testing-examples/dp/1617290890) book, Roy Osherove
- ["Unit Test Your Architecture with ArchUnit"](https://blogs.oracle.com/javamagazine/unit-test-your-architecture-with-archunit) article, Jonas Havers
- ["Unit Testing Principles, Practices, and Patterns"](https://www.amazon.com/Unit-Testing-Principles-Practices-Patterns/dp/1617296279) book, Vladimir Khorikov
- ["Growing Object-Oriented Software, Guided by Tests"](https://www.amazon.com/Growing-Object-Oriented-Software-Guided-Tests/dp/0321503627) book, Steve Freeman, Nat Pryce

### UML

- ["UML Distilled: A Brief Guide to the Standard Object Modeling Language (3rd Edition)"](https://www.amazon.com/UML-Distilled-Standard-Modeling-Language/dp/0321193687) book, Martin Fowler

### Event Storming

- ["Introducing EventStorming"](https://leanpub.com/introducing_eventstorming) book, Alberto Brandolini
- ["Awesome EventStorming"](https://github.com/mariuszgil/awesome-eventstorming) GH repository, Mariusz Gil

### Event Sourcing

- ["Hands-On Domain-Driven Design with .NET Core: Tackling complexity in the heart of software by putting DDD principles into practice"](https://www.amazon.com/Hands-Domain-Driven-Design-NET-ebook/dp/B07C5WSR9B) book, Alexey Zimarev
- ["Versioning in an Event Sourced System"](https://leanpub.com/esversioning) book, Greg Young
- [Hands-On-Domain-Driven-Design-with-.NET-Core](https://github.com/PacktPublishing/Hands-On-Domain-Driven-Design-with-.NET-Core) GH repository, Alexey Zimarev
- [EventSourcing.NetCore](https://github.com/oskardudycz/EventSourcing.NetCore) GH repository, Oskar Dudycz
