---
layout: post
title:  "FastData jest dla Ciebie głupku"
date:   2018-03-30 11:15:51 +0200
categories: FastData, Reactive
---

Tak Fast Data jest dla Ciebie głupku. Jest następnym krokiem po Big Data, a jednocześnie nie zastępuje Big Data, bo nie po to została stworzona. I to właśnie narzędzia open source pomagają korporacją i firmą przetwarzać dane na Fast Dacie.

W 1998 ósmym roku miałem może 16 lat. W 1998 roku nikt nie wyobrażał sobie, że będzie musiał przetwarzać petabajty danych historycznych przy użyciu sprzętu komputerowego. Obecnie istnieją klastry hadoopa, które są w stanie przetwarzać petabajty danych za pomocą komputerów i wirtualizacji. Biedne technologie Open Source, takie jak haddop umożliwiły tanie przetwarzanie takich zbiorów danych. W rezultacie pojawiła się dziedzina o nazwie BigData. Dopiero w nią wchodzisz prawda?

No to słuchaj chłopaku, dziewczyno, obecnie trwa podobna ewolucja i dotyczy tzw. Fast Data. Najpierw określmy, czym w ogóle jest Fast Data. Otóż dane wchodzące w skład BigData bardzo często są generowane bardzo, ale to bardzo szybko. Są to zwykle dane, które służą do obsługi kont użytkowników, analityk systemowych, danych z giełdy finansowej, czy z czujników przemysłowych. Często są one generowane od kilku tysięcy do kilku milionów na sekundę. Ten rodzaj danych jest nazywany zwykle „fire hose”.

Kiedy mówimy o „fire hose” i jednocześnie mówimy o dużych zbiorach danych, to nie mierzymy ich objętości w typowych gigabajtach, terabajtach i peta bajtach, które są znane z hurtowni danych. Objętość danych mierzymy pod względem czasu i objętości. W tym przypadku objętość mierzymy w liczbie megabajtów na sekundę, gigabajtów na minutę i terabajtów na dobę. Jeśli mówimy o Big Data, to mówimy o wytwarzania oraz objętości. Ale duże dane nie mogą być tylko duże. Dane muszą być cholernie szybkie.

Po co mi duże dane, czekające na swoją kolei? Jeśli duże dane zrzucamy tylko do HDFS, analitycznych silników RDBMS, a nawet płaskich plików, to utracimy wszystkie korzyści, jakie płyną z dużych danych, ponieważ utracimy możliwość działania w danej chwili.  De facto należy zawsze najpierw przetworzyć wszystkie aktywne dane, natychmiastowe statusy i dane, które zawierają bieżące akcje i cele. Natomiast hurtownie danych i to, co zwykle nazywa się analizą Big Data, polega na przeglądaniu danych historycznych, które pozwalają zrozumieć przeszłość i przewidzieć przyszłość. Proste co nie?

Chodźmy o krok dalej. Działania na danych w czasie rzeczywistym zwykle uważano za niemożliwe, niepraktyczne i kosztowne. Zastosowano więc to samo rozwiązanie, jakie stosuje się podczas przetwarzania Big Data. Otóż przeprojektowuje się kolejki komunikatów i wdraża systemy strumieniowe, takie jak Apache Kafka, Storm , czy Spark. Do tego wdraża się bazy danych NoSQL lub NewSQL, które także są open source.

Więc jak należy przechwytywać szybkie dane? Otóż najlepszym sposobem na przechwycenie wartości przychodzących danych jest zareagowanie na nie natychmiast po nadejściu. Jeśli zaczynamy przetwarzać dane w partiach, to tracimy czas, a tym samym wartość danych.

Aby w ten sposób przetwarzać dane, których szybkość wynosi od dziesiątek tysięcy do milionów zdarzeń na sekundę, zasadniczo potrzeba dwóch technologii, a mianowicie systemu przesłania strumieniowego, który umie przechwytywać zdarzenia w czasie rzeczywistym i systemu magazynowania danych, który także jest w stanie zapisywać i odczytywać elementy tak szybko, jak tylko się pojawią.

<h2>Dostarczanie szybkich danych</h2>

Na przestrzeni ostatnich lat pojawił się Lightbend. Przemigrowały na niego dwie platformy, a mianowicie Twitter i LinkedIn. W ten sposób powstał Apache Storm, opracowany przez inżynierów Twittera i Apache Kafka, opracowana przez inżynierów LinkedIn. Storm jest narzędziem, które może niezawodnie przetwarzać nieograniczone strumienie danych z szybkością milionów wiadomości na sekundę. Kafka jest z koli systemem kolejki komunikatów rozproszonych. Oba systemy umieją przetwarzać tzw. szybkie dane. Jednak zwykle używa się Kafki. 

Kafka jest kolejką komunikatów, która ma rozwiązywać problemy istniejących technologii. Jest to uber kolejka z nieograniczoną skalowalnością, rozproszonymi wdrożeniami, wielowątkowością oraz trwałością. Wasza organizacja może wdrożyć jeden mały kluster Kafki i zaspokoić wszystkie potrzeby organizacji w kwestii kolejkowania komunikatów. Mimo to Kafka tylko i wyłącznie dostarcza wiadomości. Nie obsługuje przetwarzania ani żadnych zapytań.

<h2>Przetwarzanie Fast Data</h2>

Należy pamiętać, że system wiadomości to tylko część rozwiązania. Tradycyjne relacyjne bazy danych posiadają ograniczoną wydajność. Oczywiście większość z nich nadaje się idealnie do przechowywania danych, ale nie można od nich oczekiwać, że nagle w magiczny sposób będą jakoś wzbogacać te dane lub wykonywać na nich działania podczas ich przetwarzania. Oczywiście mamy do dyspozycji systemy NoSQL, które zwykle działają w klastrach i posiadają wysoką wydajność, ale odbywa się to kosztem bezpieczeństwa i pieniędzy. Oczywiście w przypadku podstawowych zastosowań baza NosQL idealnie obsłuży większość przypadków biznesowych, ale w przypadku, kiedy należy szybko zareagować lub w przypadku rozległych przypadków biznesowych rozwiązania NoSQL mogą stwarzać problemy. A więc można zastosować nakładkę, jaką jest Kafka lub bazy danych typu NewSQL.

Bazy danych NewSQL są bardzo podobne w swoim działaniu do Kafki i są zbudowane wokół klastrów współdzielonych. Każde zapytanie jest dystrybuowane wewnątrz klastra, aby zapewnić jak największą wydajność. Wszystkie dane są replikowane między poszczególnymi węzłami klastra, aby zapewnić odpowiedni poziom bezpieczeństwa i dostępności. Aby obsłużyć rosnące obciążenie węzły muszą być dodawane automatycznie wewnątrz każdego klastra. Dzięki temu węzły mogą zostać uszkodzone lub usunięte, a reszta klastra będzie dalej działać. Zarówno bazy danych jak i kolejki komunikatów są projektowane bez pojedynczych punktów awarii. Przy okazji baz NoSQL wymieniliśmy więc główne cechy systemów zaprojektowanych na to, aby być skalowalnymi.

Dodatkowo należy pamiętać, że zarówno Kafka jak i systemy NewSQL wykorzystują klastry oraz dynamiczną topologię do natychmiastowego skalowania bez konieczności rezygnacji z wielu udogodnień. Kafka zapewnia gwarancję przetwarzania wiadomości, a niektóre mechanizmy przetwarzania danych w pamięci pozwalają zapewnić powtarzalność i semantykę ACID. Oba systemy używają swoich klientów obsługujących klastry, aby dostarczać jak najwięcej funkcji oraz uprościć konfigurację. Na koniec oba rozwiązania uzyskują  tzw. nadmiarową trwałość poprzez pracę na dyskach na różnych komputerach, a nie na macierzach RAID lub innych lokalnych systemach pamięci masowej.

<h2>Dobieramy odpowiednie rozwiązanie</h2>

Czego tak naprawdę poszukujemy podczas przetwarzania FastData? Oto mała lista kontrolna:

<ul>
<li>System musi posiadać zalety nadmiarowości i skalowalności natywnego klastra, który jest oparty o współużytkowanie.</li>
<li>System musi opierać się na przechowywaniu i przetwarzaniu w pamięci, co pozwala uzyskać wysoką przepustowość na każdym węźle.</li>
<li>System musi oferować przetwarzanie w czasie rzeczywistym. Czy system może wykonywać logikę warunkową? Czy może przesyłać gigabajty informacji na temat danego stanu, aby informować na bieżąco o swoich decyzjach?</li>
<li>System musi izolować od siebie poszczególne operacje i zapewniać silne gwarancje dotyczące jego działania. Wszystko to pozwala programistom prostszy kod i skupiać się na problemach biznesowych, zamiast kombinować, jak poradzić sobie z problemami przetwarzania współbieżnego oraz rozbieżności danych. Należy unikać systemów, które zapewniają wysoką spójność ale nie zapewniają wysokiej wydajności.</li>
</ul>

Systemy, które posiadają te właściwości, bardzo często pojawiają się w środowisku Open Source. Szczególnie można mówić tutaj o systemach takich jak Hadoop, NoSQL i NewSQL, ale należy pamiętać, że każdy z tych systemów posiada wbudowane pewne kompromisy. Jeżeli dana organizacja chce działać na szybkich danych w czasie rzeczywistym, to większość z tych narzędzi usuwa problem złożoności. 

<h2>Podsumowanie</h2>

Kafka jest w stanie zapewnić bezpieczny i wysoce dostępny system przenoszenia danych między nieskończoną ilością producentów i konsumentów, oferując jednocześnie wydajność i niezawodność, co zdecydowanie ułatwia administrację. Bazy danych, operujące w pamięci, mogą zaoferować szybki silnik relacyjny z potężną logiką transakcyjną, liczeniem danych i ich agregacją, a jednocześnie posiadają odpowiednią skalowalność, aby sprostać dowolnemu obciążeniu. Ale systemy te tylko w niewielkiej części powinny działać jako relacyjne bazy danych. Przede wszystkim muszą działać jako mechanizmy przetwarzania, uzupełniające infrastrukturę Kafki. Bez względu na to, jakie są potrzeby Twojej organizacji, niektóre kombinacje tych narzędzi mogą Ci naprawdę pomóc. Dzięki nim możesz wiedzieć więcej niż wiesz dotychczas i można w ten sposób zastępować inne bardziej kruche systemy.
