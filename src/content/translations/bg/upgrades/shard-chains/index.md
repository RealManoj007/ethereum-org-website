---
title: Вериги от компоненти
description: Научете какво са веригите от компоненти – части от мрежата, които дават по-голям капацитет на трансакциите при Етереум и я правят по-лесна за работа.
lang: bg
template: upgrade
sidebar: true
image: ../../../../../assets/eth2/newrings.png
summaryPoint1: Разделянето на компоненти е многофазен ъпгрейд с цел подобряване на мащаба и капацитета на Етереум.
summaryPoint2: Веригите от компоненти разпределят обема на мрежата на 64 нови вериги.
summaryPoint3: Те улесняват работата на един нод чрез поддържане на ниски изисквания към хардуера.
summaryPoint4: Техническите карти включват работа върху вериги от компоненти във "Фаза 1" и потенциално "Фаза 2".
---

<UpgradeStatus date="~2023">
    Веригите от компоненти ще бъдат пуснати по някое време през 2023 г. в зависимост от това колко бързо върви работата след като <a href="/upgrades/beacon-chain/">Сигналната верига</a> бъде внедрена. Тези компоненти ще увеличат капацитета на Етереум да съхранява и намира данни, но те няма да бъдат използвани при кодиране. Подробностите за това още се уточняват.
</UpgradeStatus>

## Какво представлява фрагментирането? {#what-is-sharding}

Фрагментирането е процес на хоризонтално разделяне на база данни, за да се разпредели натоварването – това е често срещан метод в компютърните науки. В контекста на Етереум фрагментирането ще намали задръстването на мрежата и ще увеличи броя трансакции в секунда чрез създаването на нови вериги, известни като "компоненти".

Това е важно и поради други причини освен мащаба.

## Характеристики на фрагментирането {#features-of-sharding}

### Всеки може да създаде нод {#everyone-can-run-a-node}

Фрагментирането е добър начин за увеличаване на мащаба, ако държите на децентрализацията, тъй като алтернативата е мащабът да се увеличи чрез увеличаване на размера на съществуващата база данни. Това ще направи Етереум по-малко достъпен за валидаторите на мрежата, защото те ще се нуждаят от мощни и скъпи компютри. С веригите от компоненти валидаторите ще трябва да съхраняват/работят с данни само за компонента, който валидират, а не за цялата мрежа (както се случва сега). Това ускорява процеса и драстично намалява изискванията към хардуера.

### Повече участие в мрежата {#more-network-participation}

Впоследствие фрагментирането ще позволи свалянето на Етереум на личния лаптоп или телефон. Така че повече хора ще могат да участват или да управляват [клиенти](/developers/docs/nodes-and-clients/) в един фрагментиран Етереум. Това ще увеличи сигурността, защото колкото по-децентрализирана е мрежата, толкова по-малка ще е площта за атака.

С по-малкото изисквания към хардуера фрагментирането ще направи по-лесно управлението на [клиенти](/developers/docs/nodes-and-clients/) сам, без въобще да се разчита на услугите на междинни звена. И ако можете, да прецените обслужване и на няколко клиента. Това ще заздрави мрежата чрез намаляване на слабите звена. [Активирай клиент на Eth2](/eth2/get-involved/)

<br />

<InfoBanner isWarning={true}>
  Като начало ще трябва да активирате клиент на основната мрежа едновременно с клиента на Eth2. <a href="https://launchpad.ethereum.org" target="_blank">Платформата</a> ще ви води през изискванията към хардуера и целия процес. Възможно е и да използвате <a href="/developers/docs/apis/backend/#available-libraries">бекенд API</a>.
</InfoBanner>

## Вериги от компоненти версия 1: наличност на данните {#data-availability}

Когато се пуснат първите вериги от компоненти, те ще заредят мрежата с допълнителни данни. Те няма да се занимават с трансакции или умни договори. Но те все още ще предлагат невероятни подобрения към трансакциите за секунда, когато се съчетаят с ролаповете.

Ролаповете са технология на "ниво 2", каквато съществува днес. Те позволяват на дапс (децентрализираните приложения) да опаковат или "ролап" няколко трансакции в една извън веригата, да генерират криптографско доказателство и след това да я пуснат във веригата. Това намалява данните, необходими за една трансакция. Ако комбинирате това с всички допълнителни възможности за данни, осигурени от компонентите, ще получите 100 000 трансакции на секунда.

[Повече за ролаповете](/developers/docs/layer-2-scaling/)

## Вериги от компоненти версия 2: изпълнение на кодове {#code-execution}

Планът винаги е бил да се добави допълнителна функционалност на компонентите, те да приличат повече на [основната мрежа на Етереум](/glossary/#mainnet) днес. Това ще им позволи да съхраняват и изпълняват умни договори и да работят с акаунти. Но ако имаме предвид увеличаването на трансакциите на секунда, които предлагат компонентите във версия 1, това наистина ли е необходимо? Това все още се обсъжда в общността и, както изглежда, има няколко възможности.

### Компонентите нуждаят ли се от изпълнение на кодове? {#do-shards-need-code-execution}

В подкаста на Банклес Виталик Бутерин представи 3 потенциални възможности, които си струва да бъдат обсъдени.

<iframe width="100%" height="315" src="https://www.youtube.com/embed/-R0j5AMUSzA?start=5841" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen mark="crwd-mark"></iframe>

#### 1. Няма да има нужда от изпълнение на умни договори {#state-execution-not-needed}

Това означава, че компонентите няма да имат възможност да управляват умните договори и да ги съхраняват като склад за данни.

#### 2. Ще има няколко компонента за изпълнение {#some-execution-shards}

Може би има компромис в това, че нямаме нужда от всички компоненти (сега се планират 64), за да бъде по-разумно. Можем просто да добавим тази функционалност към някои от тях и да оставим другите. Това би могло да ускори предаването.

#### 3. Почакайте, докато можем да извършим Zero Knowledge (ZK) snarks {#wait-for-zk-snarks}

И накрая, може да се върнем към този спор, когато се утвърдят тези ZK snarks. Това е технология, която наистина може да улесни вкарването на частни трансакции в мрежата. Вероятно е те да изискват по-умни компоненти, но те все още са в процес на изучаване и развитие.

#### Други източници {#other-sources}

Ето няколко повода за размисъл в същата посока:

- [Фаза Едно и Това е: Eth2 като data availability engine](https://ethresear.ch/t/phase-one-and-done-eth2-as-a-data-availability-engine/5269/8) – _cdetrio, ethresear.ch_

Това все още е точка на активно обсъждане. Ще ъпдейтваме тези страници, когато знаем повече.

## Връзка между ъпгрейдите {#relationship-between-upgrades}

Ъпгрейдите на Eth2 са взаимосвързани по определен начин. Така че нека обобщим как веригите от компоненти се отнасят към другите ъпгрейди.

### Компонентите и Сигналната верига {#shards-and-beacon-chain}

Сигналната верига съдържа цялата логика на опазване на сигурността на компонентите и тяхното синхронизиране. Сигналната верига ще координира залагащите в мрежата, като ги свързва с компонентите, върху които те трябва да работят. А това също така ще улеснява комуникацията между компонентите чрез получаване и съхраняване на данните за трансакциите, които ще бъдат достъпни за другите компоненти. Това ще даде на компонентите поглед върху Етереум, за да могат да поддържат състоянието му актуално.

<ButtonLink to="/upgrades/beacon-chain/">Сигналната верига</ButtonLink>

### Компонентите и техният докинг {#shards-and-docking}

Основната мрежа на Етереум ще съществува както и сега, даже след въвеждането на компонентите. Обаче в един момент основната мрежа ще трябва да се превърне в компонент, за да може да премине към залагане. Тепърва ще се види дали основната мрежа ще съществува като единствения "умен" компонент, който може да изпълнява кодове – но и в двата случая ще трябва да се вземе решение относно фаза 2 на фрагментирането.

<ButtonLink to="/eth2/docking/">Докингът</ButtonLink>

<Divider />

### Прочети още {#read-more}

<Eth2ShardChainsList />