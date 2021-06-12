# Mobile Application Security Verification Standard


MASVS może zostać użyty do ustanowienia poziomu ufności w bezpieczeństwie aplikacji mobilnych. Wymagania były rozwijane z myślą o  następujących celach: 

- Użycia jako metryki - Dla zapewnienia standardu bezpieczeństwa przeciwko któremu aplikacje mobilne mogą być porównywane przez developerów i właścicieli aplikacji;
- Użycia jako przewodnika - Dla zapewnienia przewodnictwa podczas każdej z faz rozwoju i testowania aplikacji mobilnej
- Użycia podczas nabywania - Dla zapewnienia podstaw bezpieczeństwa dla weryfikacji bezpieczeństwa aplikacji mobilnych.

## Model Mobilnego AppSec

MASVS definiuje dwa poziomy weryfikacji bezpieczeństwa (MASVS-L1 oraz MASVS-L2), jak również zestaw wymagań wobec niezawodności wobec inżynierii wstecznej (MASVS-R). MASVS-L1 zawiera ogólne wymagania bezpieczeństwa które są zalecane dla każdej mobilnej aplikacji, podczas gdy MASVS-L2 należy zastosować dla aplikacji przetwarzających mocno wrażliwe dane. MASVS-R pokrywa dodatkowe kontrole ochronne które mogą być aplikowane gdy zapobieganie zagrożeniom po stronie-klienckiej jest celem projektowym.

Spełnienie wymagań MASVS-L1 skutkuje powstaniem bezpiecznej aplikacji, która jest zgodna z najlepszymi praktykami bezpieczeństwa i nie ma typowych luk w zabezpieczeniach. MASVS-L2 dodaje dodatkowe dogłębne mechanizmy ochrony, takie jak SSL Pinning, dzięki czemu aplikacja jest odporna na bardziej wyrafinowane ataki – zakładając, że mechanizmy bezpieczeństwa mobilnego systemu operacyjnego są nienaruszone, a użytkownik końcowy nie jest postrzegany jako potencjalny przeciwnik . Spełnienie wszystkich lub podzbiorów wymagań dotyczących ochrony oprogramowania w MASVS-R pomaga zapobiegać konkretnym zagrożeniom po stronie klienckiej, w których użytkownik końcowy jest złośliwy i/lub mobilny system operacyjny jest zagrożony.


**I: Chociaż zalecamy wdrożenie kontroli MASVS-L1 w każdej aplikacji, decyzja o wdrożeniu kontroli lub nie powinna ostatecznie być decyzją opartą na ryzyku, która jest podejmowana/komunikowana właścicielom firmy.**

**II: Należy pamiętać, że kontrole ochrony poprzez oprogramowania wymienione w MASVS-R i opisane w OWASP Mobile Security Testing Guide mogą zostać ostatecznie ominięte i nigdy nie mogą być używane jako zamiennik pierwotnych kontroli bezpieczeństwa. Zamiast tego mają one na celu dodanie dodatkowych warstw, chroniących przed podatnościami aplikacji, które również spełniają wymagania MASVS w MASVS-L1 lub MASVS-L2.**

![Verification Levels](images/masvs-levels-new.jpg)

### Struktura Dokumentu

Pierwsza część MASVS zawiera opis modelu bezpieczeństwa i dostępnych poziomów weryfikacji, a następnie zalecenia dotyczące praktycznego wykorzystania standardu. Szczegółowe wymagania bezpieczeństwa wraz z odwzorowaniem do poziomów weryfikacji są wymienione w drugiej części. Wymagania zostały pogrupowane w osiem kategorii (od V1 do V8) w oparciu o cel/zakres techniczny. W MASVS i MSTG stosowana jest następująca nomenklatura:

- *Kategoria wymagań:* MASVS-Vx, np. MASVS-V2: przechowywanie danych i prywatność
- *Wymaganie:* MASVS-Vx.y, np. MASVS-V2.2: „Żadne poufne dane nie powinny być zapisywane w logach aplikacji”.

### Szczegóły poziomów weryfikacji

#### MASVS-L1: Standardowe zabezpieczenia

Aplikacja mobilna, która osiąga MASVS-L1 jest zgodna z najlepszymi praktykami bezpieczeństwa aplikacji mobilnych. Spełnia podstawowe wymagania w zakresie jakości kodu, obsługi wrażliwych danych oraz interakcji ze środowiskiem mobilnym. Musi istnieć proces testowania w celu weryfikacji kontroli bezpieczeństwa. Ten poziom jest odpowiednim dla wszystkich aplikacji mobilnych.

#### MASVS-L2: Obrona-Wielowarstwowa
MASVS-L2 wprowadza zaawansowane kontrole bezpieczeństwa, które wykraczają poza standardowe wymagania. Aby spełnić wymagania MASVS-L2, musi istnieć model zagrożenia, a bezpieczeństwo musi być integralną częścią architektury i projektu aplikacji. W oparciu o model zagrożenia, odpowiednie kontrole MASVS-L2 powinny zostać wybrane i pomyślnie wdrożone. Ten poziom jest odpowiedni dla aplikacji obsługujących bardzo wrażliwe dane, takich jak mobilne aplikacje bankowe.

#### MASVS-R: Niezawodność przeciwko Inżynierii Wstecznej i Fałszowania

Aplikacja ma najnowocześniejsze zabezpieczenia, a także jest odporna na określone, jasno zdefiniowane ataki po stronie klienckiej, takie jak fałszowanie, modowanie lub inżynieria wsteczna w celu wydobycia wrażliwego kodu lub danych. Taka aplikacja wykorzystuje funkcje zabezpieczeń sprzętowych lub wystarczająco silne i weryfikowalne techniki ochrony dzięki oprogramowaniu. MASVS-R ma zastosowanie do aplikacji, które obsługują bardzo wrażliwe dane i może służyć jako środek ochrony własności intelektualnej lub zabezpieczenia aplikacji przed sfałszowaniem.

### Zalecane Użycie

Aplikacje mogą być weryfikowane pod kątem MASVS L1 bądź L2 na podstawie wcześniejszej oceny ryzyka i wymaganego ogólnego poziomu bezpieczeństwa.L1 ma zastosowanie do wszystkich aplikacji mobilnych, podczas gdy L2 jest ogólnie zalecany dla aplikacji, które obsługują bardziej wrażliwe dane i/lub funkcje. MASVS-R (lub jego części) można zastosować *dodatkowo* do weryfikacji niezawodności na określone zagrożenia, takie jak przepakowywanie lub wydobycie wrażliwych danych.


Podsumowując, dostępne są następujące rodzaje weryfikacji:

- MASVS-L1
- MASVS-L1+R
- MASVS-L2
- MASVS-L2+R

Różne kombinacje odzwierciedlają różne stopnie bezpieczeństwa i odporności. Celem jest zapewnienie elastyczności: na przykład gra mobilna może nie uzasadniać dodawania kontroli bezpieczeństwa MASVS-L2, takich jak uwierzytelnianie dwuskładnikowe, ze względu na użyteczność, ale ma silną potrzebę biznesową w zakresie zapobiegania sfałszowaniu.

#### Który typ weryfikacji wybrać

Implementacja wymagań MASVS L2 zwiększa bezpieczeństwo, jednocześnie zwiększając koszty rozwoju i potencjalnie pogarszając wrażenia użytkownika końcowego (klasyczny kompromis). Ogólnie rzecz biorąc, L2 powinno być używane w aplikacjach zawsze, gdy ma to sens z perspektywy ryzyka i kosztów (tj. gdy potencjalna strata spowodowana naruszeniem poufności lub integralności jest wyższa niż koszt poniesiony przez dodatkowe zabezpieczenia). Ocena ryzyka powinna być pierwszym krokiem przed zastosowaniem MASVS.

##### Przykłady

###### MASVS-L1

- Wszystkie aplikacje mobilne. MASVS-L1 zawiera listę najlepszych praktyk w zakresie bezpieczeństwa, których można przestrzegać, mając rozsądny wpływ na koszty rozwoju i wrażenia użytkownika. Zastosuj wymagania MASVS-L1 dla dowolnej aplikacji, która nie kwalifikuje się do jednego z wyższych poziomów.

<!-- \pagebreak -->

###### MASVS-L2

- Branża opieki zdrowotnej: aplikacje mobilne, które przechowują informacje umożliwiające identyfikację osób, które można wykorzystać do kradzieży tożsamości, nieuczciwych płatności lub różnych schematów oszustw. W przypadku sektora opieki zdrowotnej w Stanach Zjednoczonych kwestie zgodności obejmują ustawę o przenośności i odpowiedzialności w ubezpieczeniach zdrowotnych (HIPAA) dotyczącą prywatności, bezpieczeństwa, zasad powiadamiania o naruszeniu oraz zasady bezpieczeństwa pacjenta.

- Branża finansowa: aplikacje umożliwiające dostęp do bardzo poufnych informacji, takich jak numery kart kredytowych czy dane osobowe, lub umożliwiające użytkownikowi przenoszenie środków. Te aplikacje gwarantują dodatkowe kontrole bezpieczeństwa, aby zapobiec oszustwom. Aplikacje finansowe muszą zapewniać zgodność ze standardami Payment Card Industry Data Security Standard (PCI DSS), Gramm Leech Bliley Act i Sarbanes-Oxley Act (SOX).

###### MASVS L1+R

- Aplikacje mobilne, w których ochrona własności intelektualnej (IP) jest celem biznesowym. Kontrole odporności wymienione w MASVS-R można wykorzystać do zwiększenia wysiłku potrzebnego do uzyskania oryginalnego kodu źródłowego i utrudnienia manipulacji / crackingu.

- Branża gier: Gry, w których niezbędna jest ochrona przed modyfikacją i oszustwami, takie jak konkurencyjne gry online. Oszukiwanie jest ważnym problemem w grach online, ponieważ duża liczba oszustów prowadzi do niezadowolonych graczy i może ostatecznie spowodować niepowodzenie gry. MASVS-R zapewnia podstawowe kontrole zapobiegające manipulacjom kodu, aby pomóc zwiększyć wysiłek oszustów.

###### MASVS L2+R

- Branża finansowa: aplikacje bankowości internetowej, które umożliwiają użytkownikowi przenoszenie środków, w przypadku których techniki, takie jak wstrzykiwanie kodu i instrumentacji na zhakowanych urządzeniach, stanowią ryzyko. W takim przypadku kontrole z MASVS-R mogą zostać użyte do utrudnienia manipulacji, podnosząc poprzeczkę dla autorów złośliwego oprogramowania.

- Wszystkie aplikacje mobilne, które z założenia muszą przechowywać wrażliwe dane na urządzeniu mobilnym, a jednocześnie muszą obsługiwać szeroką gamę urządzeń i wersji systemów operacyjnych. W takim przypadku kontrole dla niezawodności mogą być wykorzystywane jako obrona wielowarstwowa, aby zwiększyć wysiłek atakujących, którzy chcą wydobyć poufne dane.

- Aplikacje z zakupami w aplikacji powinny najlepiej używać kontroli po stronie serwera i MASVS-L2, aby chronić płatne treści. Mogą jednak wystąpić przypadki, w których nie ma możliwości skorzystania z ochrony po stronie serwera. W takich przypadkach należy dodatkowo zastosować kontrole MASVS-R w celu zwiększenia wysiłku inżynierii wstecznej i/lub naruszenia kodu.
