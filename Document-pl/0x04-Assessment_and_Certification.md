# Ocena i Certyfikacja

## Stanowisko OWASP w sprawie Certyfikatów oraz Oznaczeń Zaufania

OWASP, jako niezależna od dostawców organizacja non-profit, nie certyfikuje żadnych dostawców, audytorów ani oprogramowania.

Wszystkie takie zapewnienia, oznaczenia zaufania lub certyfikaty nie są oficjalnie weryfikowane, rejestrowane ani certyfikowane przez OWASP, więc organizacja polegająca na takim poglądzie musi być ostrożna w kwestii zaufania pokładanego w jakiejkolwiek oznaczenia zaufania twierdzących o orzecznictwie (M)ASVS od osób trzecich.

Nie powinno to powstrzymywać organizacji przed oferowaniem takich usług atestacyjnych, o ile nie twierdzą one, że posiadają oficjalną certyfikację OWASP.

## Wskazówki dotyczące certyfikacji aplikacji mobilnych

Rekomendowanym sposobem weryfikacji zgodności aplikacji mobilnej z MASVS jest przeprowadzenie przeglądu „otwartej księgi”, co oznacza, że testerzy uzyskują dostęp do kluczowych zasobów, takich jak architekci i programiści aplikacji, dokumentacji projektowej, kodu źródłowego i uwierzytelniony dostęp do punktów końcowych, w tym dostęp do co najmniej jednego konta użytkownika dla każdej roli.

Należy zauważyć, że MASVS obejmuje tylko bezpieczeństwo aplikacji mobilnej (po stronie klienckiej) i komunikację sieciową między aplikacją a jej zdalnymi punktami końcowymi, a także kilka podstawowych i ogólnych wymagań związanych z uwierzytelnianiem użytkownika i zarządzaniem sesją. Nie zawiera szczegółowych wymagań dotyczących usług zdalnych (np. usług internetowych) związanych z aplikacją, poza ograniczonym zestawem ogólnych wymagań dotyczących autoryzacji, uwierzytelniania, weryfikacji kontroli i zarządzania sesją. Jednak MASVS V1 określa, że usługi zdalne muszą być objęte ogólnym modelem zagrożeń i zostać zweryfikowane pod kątem odpowiednich standardów, takich jak OWASP ASVS.

Organizacja certyfikująca musi zawrzeć w każdym raporcie zakres weryfikacji (szczególnie, jeśli kluczowy komponent jest poza zakresem), podsumowanie wyników weryfikacji, w tym zaliczonych i niezaliczonych testów, z wyraźnymi wskazówkami, jak rozwiązać nieudane testy. Przechowywanie szczegółowych dokumentów roboczych, zrzutów ekranu lub filmów, skryptów do niezawodnego i wielokrotnego odtworzenia problemu jak i elektronicznych zapisów testów, takich jak przechwytywanie logów proxy i powiązanych notatek, takich jak lista do oczyszczenia, jest uważane za standardową praktykę branżową.
Nie wystarczy po prostu uruchomić narzędzie i zgłosić podatność; nie dostarcza to wystarczających dowodów na to, że wszystkie kwestie na poziomie certyfikacji zostały dokładnie przetestowane dogłębnie. W przypadku sporu powinny istnieć wystarczające dowody potwierdzające, że każde zweryfikowane wymaganie zostało rzeczywiście przetestowane.

<!-- \pagebreak -->

### Korzystanie z OWASP Mobile Security Testing Guide (MSTG)

OWASP MSTG to podręcznik do testowania bezpieczeństwa aplikacji mobilnych. Opisuje techniczne procesy weryfikacji wymagań wymienionych w MASVS. MSTG zawiera listę przypadków testowych, z których każdy jest dopasowany na wymagania w MASVS. Chociaż wymagania MASVS są wysokie i ogólne, MSTG zapewnia szczegółowe zalecenia i procedury testowe na podstawie mobilnych systemów operacyjnych.

### Rola Automatycznych Narzędzi do Testowania Bezpieczeństwa

Zachęca się do korzystania ze skanerów kodu źródłowego i narzędzi do testowania black-box w celu zwiększenia wydajności, gdy tylko jest to możliwe. Nie jest jednak możliwe ukończenie weryfikacji MASVS za pomocą samych zautomatyzowanych narzędzi: każda aplikacja mobilna jest inna, a zrozumienie ogólnej architektury, logiki biznesowej i pułapek technicznych konkretnych wykorzystywanych technologii i frameworków jest obowiązkowym wymogiem weryfikacji bezpieczeństwa aplikacja.

## Inne zastosowania

### Jako szczegółowe wytyczne dotyczące architektury bezpieczeństwa

Jednym z najczęstszych zastosowań Mobile Application Security Verification Standard jest jako środek dla architektów bezpieczeństwa. Dwóm głównym strukturom architektury bezpieczeństwa, SABSA lub TOGAF brakuje dużej ilości informacji niezbędnych do ukończenia przeglądu architektury bezpieczeństwa aplikacji mobilnych. MASVS można wykorzystać do wypełnienia tych luk, umożliwiając architektom bezpieczeństwa wybór lepszych mechanizmów kontroli problemów typowych dla aplikacji mobilnych.

### Jako Zamiennik dla Gotowych Checklist Bezpiecznego Programowania

Wiele organizacji może odnieść korzyści z przyjęcia MASVS, wybierając jeden z dwóch poziomów lub rozdwajając MASVS i zmieniając to, co jest wymagane dla poziomu ryzyka każdej aplikacji w sposób specyficzny dla danej domeny. Zachęcamy do tego typu rozdwajania, o ile zachowana jest identyfikowalność, więc jeśli aplikacja spełni wymagania 4.1, oznacza to to samo dla rozdwidlonych kopii wraz z rozwojem standardu.

### Jako Podstawa Metodyk Testowania Bezpieczeństwa

Dobra metodyka testowania bezpieczeństwa aplikacji mobilnych powinna obejmować wszystkie wymagania wymienione w MASVS. Przewodnik OWASP Mobile Security Testing Guide (MSTG) opisuje przypadki testowe black-box i white-box dla każdego wymagania weryfikacji.

### Jako Przewodnik Dla Zautamotyzanych Testach Jednostkowych i Integracyjnych

MASVS został zaprojektowany tak, aby był wysoce testowalny, w szczególności w wymaganiach architektonicznych. Zautomatyzowane testy jednostkowe, integracyjne i akceptacyjne oparte na wymaganiach MASVS można zintegrować z ciągłym cyklem rowoju oprogramowania. To nie tylko zwiększa świadomość bezpieczeństwa programistów, ale także poprawia ogólną jakość powstałych aplikacji i zmniejsza liczbę wyników testów bezpieczeństwa w fazie przedpremierowej.

### Jako Szkolenie w Zakresie Bezpiecznego Tworzenia Oprogramowania

MASVS może być również używany do definiowania cech bezpiecznych aplikacji mobilnych. Wiele kursów „bezpiecznego kodowania” to po prostu kursy etycznego hakowania z niewielką ilością wskazówek dotyczących kodowania. To nie pomaga programistom. Zamiast tego kursy bezpiecznego rozwoju mogą korzystać z MASVS, z silnym naciskiem na proaktywne kontrole udokumentowane w MASVS, a nie np. "10 Najważniejszych Błędów Popełnianych Przez Programistów".