# Ocena i Certyfikacja

## Stanowisko OWASP w sprawie Certyfikatów oraz Oznaczeń Zaufania

OWASP, jako niezależna organizacja non-profit, nie certyfikuje żadnych dostawców, audytorów ani oprogramowania.

Wszystkie takie zapewnienia, oznaczenia zaufania lub certyfikaty nie są oficjalnie weryfikowane, rejestrowane ani certyfikowane przez OWASP, więc organizacja chcąc zastosować standard musi być ostrożna w kwestii zaufania pokładanego w firmie zewnętrznej, która legitymuję się certyfikacją (M)ASVS. 

Brak certyfikacji nie powienien powstrzymywać organizacji przd dostarczaniem usług weryfikacji zgodnych ze standardem, o ile nie twierdzą że posiadają oficjalny certyfikat wydany przez OWASP.

## Wskazówki dotyczące certyfikacji aplikacji mobilnych

Rekomendowanym sposobem weryfikacji zgodności aplikacji mobilnej z MASVS jest przeprowadzenie przeglądu zgodnie z metodyką „otwartej księgi”, co oznacza, że testerzy uzyskują dostęp do kluczowych zasobów, takich jak architekci i programiści aplikacji, dokumentacji projektowej, kodu źródłowego oraz uwierzytelniony dostęp do punktów końcowych, w tym dostęp do co najmniej jednego konta użytkownika dla każdej roli.

Należy zauważyć szcególną uwagę, że MASVS obejmuje wyłącznie aspekty związane z bezpieczeństwem aplikacji mobilnych (po stronie klienckiej) i komunikację sieciową między aplikacją a serwerem aplikacji, a także kilka podstawowych i ogólnych wymagań związanych z uwierzytelnianiem użytkownika i zarządzaniem sesją. Nie zawiera szczegółowych wymagań dotyczących usług zdalnych (np. usług internetowych) związanych z aplikacją, poza ograniczonym zestawem ogólnych wymagań dotyczących autoryzacji, uwierzytelniania, weryfikacji kontroli dostępu i zarządzania sesją. Jednakże, MASVS V1 określa, że usługi zdalne muszą być objęte ogólnym modelem zagrożeń i zostać zweryfikowane pod kątem odpowiednich standardów, takich jak OWASP ASVS.

Organizacja certyfikująca musi zawrzeć w każdym raporcie szczegółowy zakres weryfikacji (w szczególności jeśli kluczowy komponent aplikacji jest poza zakresem), podsumowanie wyników weryfikacji, w tym spełnionych i niespełnionych punktów, z wyraźnymi wskazówkami jak rozwiązać niezaliczone testy. Przechowywanie szczegółowych dokumentów roboczych, zrzutów ekranu lub filmów, skryptów do wiarygodnego i wielokrotnego odtworzenia problemu jak i elektronicznych zapisów testów, takich jak przechwycone logi proxy i powiązanych notatek, jest uważane za standardową praktykę branżową.
Nie jest uznawane za wystarczające uruchomienie narzędzia i zgłoszenie podatność; nie dostarcza to wystarczających dowodów na to, że wszystkie kwestie na poziomie certyfikacji zostały dokładnie oraz dogłębnie przetestowane. W przypadku sporu, powinny istnieć wystarczające dowody potwierdzające, że każde zweryfikowane wymaganie zostało rzeczywiście przetestowane.

<!-- \pagebreak -->

### Korzystanie z OWASP Mobile Security Testing Guide (MSTG)

OWASP MSTG to podręcznik opisujący proces testowania bezpieczeństwa aplikacji mobilnych. Opisuje techniczne procesy weryfikacji wymagań wymienionych w MASVS. MSTG zawiera listę przypadków testowych, z których każdy jest dopasowany do konkretnego wymagania w MASVS. Chociaż wymagania MASVS są wysoko-poziomowe i ogólne, MSTG zapewnia szczegółowe zalecenia i procedury testowe dla konkretnych systemów operacyjnych.

### Rola Automatycznych Narzędzi do Testowania Bezpieczeństwa

Zachęca się do korzystania ze skanerów kodu źródłowego i narzędzi do testowania black-box w celu zwiększenia skuteczności testów, gdy tylko jest to możliwe. Nie jest jednak możliwe ukończenie weryfikacji MASVS za pomocą użycia wyłącznie zautomatyzowanych narzędzi: każda aplikacja mobilna jest inna, a zrozumienie ogólnej architektury, logiki biznesowej i czychających pułapek technicznych specyficznych dla konkretnych wykorzystywanych technologii i frameworków jest obowiązkowym wymogiem weryfikacji bezpieczeństwa aplikacja.

## Inne zastosowania

### Jako szczegółowe wytyczne dotyczące architektury bezpieczeństwa

Jednym z najczęstszych zastosowań Standardu Weryfikacji Bezpieczeństwa Aplikacji Mobilnych (MASVS) jest jako podstawa dla architektów bezpieczeństwa. Dwa główne frameworki dotyczące bezpieczeństwa architektury - SABSA oraz TOGAF nie zawierają wielu informacji niezbędnych do ukończenia przeglądu architektury bezpieczeństwa aplikacji mobilnych. MASVS może zostać wykorzystany do wypełnienia tych luk, umożliwiając architektom bezpieczeństwa wybór lepszych mechanizmów kontroli problemów typowych dla aplikacji mobilnych.

### Jako Zamiennik dla Gotowych Checklist Bezpiecznego Programowania

Wiele organizacji może odnieść korzyści z przyjęcia MASVS, wybierając jeden z dwóch dostępnych poziomów lub dopasowując MASVS poprzez zmianę tego, co jest wymagane dla poziomu ryzyka każdej aplikacji w sposób specyficzny dla jej zastosowania. Zachęcamy do tego typu dopasowania, o ile zachowane są odniesienia do oryginalnego dokumentu, więc jeśli aplikacja spełni wymaganie 4.1, oznacza to wymaganie jest spełnione zarówno dla dopasowanego dokumentu, jak i aktualnej wersji oryginalnego MASVS.

### Jako Podstawa Metodyk Testowania Bezpieczeństwa

Dobra metodyka testowania bezpieczeństwa aplikacji mobilnych powinna obejmować wszystkie wymagania wymienione w MASVS. Przewodnik OWASP Mobile Security Testing Guide (MSTG) opisuje przypadki testowe zarówno w metodyce black-box i white-box dla każdego wymagania weryfikacji.

### Jako Przewodnik Dla Zautamotyzanych Testów Jednostkowych i Integracyjnych

MASVS został zaprojektowany tak, aby był wysoce testowalny, z jednym wyjątkiem jakim są wymagania architektoniczne. Zautomatyzowane testy jednostkowe, integracyjne i akceptacyjne oparte na wymaganiach MASVS można zintegrować z ciągłym cyklem rowoju oprogramowania. To nie tylko zwiększa świadomość bezpieczeństwa aplikacji wśród programistów, ale także poprawia ogólną jakość powstałych aplikacji i zmniejsza liczbę zidentyfikowanych podatności w testach bezpieczeństwa w fazie przedprodukcyjnej.

### Jako Szkolenie w Zakresie Bezpiecznego Tworzenia Oprogramowania

MASVS może być również używany do definiowania cech bezpiecznych aplikacji mobilnych. Wiele kursów „bezpiecznego kodowania” to po prostu kursy etycznego hakowania z niewielką ilością wskazówek dotyczących kodowania. Taka forma szkolenia nie pomaga programistom. Zamiast tego kursy bezpiecznego kodowania mogą korzystać z MASVS, z mocnym naciskiem na proaktywne kontrole udokumentowane w MASVS, a nie np. "10 najważniejszych błędów popełnianych pzez programistów".
