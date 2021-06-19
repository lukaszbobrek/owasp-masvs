# V8: Wymagania dotyczące Niezawodności

## Cele Kontrolne

W tej sekcji omówiono szczegółowe środki ochrony zalecane w przypadku aplikacji, które przetwarzają wrażliwe dane lub funkcje bądź umożliwiają dostęp do nich. Brak którejkolwiek z tych kontroli nie powoduje powstania luki w zabezpieczeniach — zamiast tego mają one na celu zwiększenie odporności aplikacji na inżynierię wsteczną i określone ataki po stronie klienckiej.

Kontrole w tej sekcji należy stosować w razie potrzeby na podstawie oceny ryzyka spowodowanego nieautoryzowaną manipulacją kodu aplikacji i/lub inżynierią wsteczną kodu. Sugerujemy zapoznanie się z dokumentem OWASP „Technical Risks of Reverse Engineering and Unauthorized Code Modification Reverse Engineering and Code Modification Prevention” (patrz odnośniki poniżej) w celu uzyskania listy ryzyk biznesowych oraz powiązanych zagrożeń technicznych.

Aby którakolwiek z kontroli z poniższej listy była skuteczna, aplikacja musi spełniać co najmniej wszystkie wymagania MASVS-L1 (tj. muszą istnieć solidne kontrole bezpieczeństwa), a także wszystkie wymagania o niższych numerach w V8. Na przykład, kontrole obfuskacji wymienione w punkcie „Utrudnianie Zrozumienia” muszą być połączone z „Utrudnianie Analizy Dynamicznej i Manipulacji Kodu” i „Wiązanie Urządzenia (Device Binding)”.

**Należy pamiętać, że ochrony oprogramowania nigdy nie wolno używać jako zamiennika kontroli bezpieczeństwa. Kontrole wymienione w MASVR-R mają na celu dodanie specyficznych dla zagrożeń, dodatkowych kontroli ochronnych do aplikacji, które również spełniają wymagania bezpieczeństwa MASVS.**

Obowiązują następujące względy:

1. Należy zdefiniować model zagrożeń, który jasno określa zagrożenia po stronie klienckiej, przed którymi się bronimy. Ponadto należy określić stopień ochrony, jaki ma zapewniać system. Na przykład określonym celem może być zmuszenie autorów ukierunkowanego złośliwego oprogramowania, które chcą podszyć się pod aplikację, do zainwestowania znacznego wysiłku w ręczną inżynierię wsteczną.

2. Model zagrożenia musi być wiarygodny i odpowiedni. Na przykład ukrywanie klucza kryptograficznego w implementacji white-box może okazać się zbędne, jeśli atakujący może po prostu dokonać code-liftu na white-boxie jako całości.

3. Skuteczność ochrony powinna być zawsze weryfikowana przez eksperta posiadającego doświadczenie w testowaniu poszczególnych rodzajów stosowanych zabezpieczeń przed manipulacją kodu i obfuskacji (patrz także rozdziały „Inżynieria Wsteczna” i „Ocena Zabezpieczeń Oprogramowania” w Mobile Security Testing Guide).

<!-- \pagebreak -->

### Utrudnianie Analizy Dynamicznej i Manipulacji Kodu

| # | MSTG-ID | Description | R |
| -- | ----------- | ---------------------- | - |
| **8.1** | MSTG-RESILIENCE-1 | Aplikacja wykrywa i reaguje na obecność zrootowanego  lub jailbreakowanego urządzenia, ostrzegając użytkownika lub zamykając aplikację. | x |
| **8.2** | MSTG-RESILIENCE-2 | Aplikacja zapobiega debugowaniu i/lub wykrywa i odpowiada na dołączony debuger. Należy uwzględnić wszystkie dostępne protokoły debugowania. | x |
| **8.3** | MSTG-RESILIENCE-3 | Aplikacja wykrywa i reaguje na manipulowanie plikami wykonywalnymi i krytycznymi danymi we własnym sandboxie. | x |
| **8.4** | MSTG-RESILIENCE-4 | Aplikacja wykrywa i reaguje na obecność na urządzeniu szeroko stosowanych narzędzi i frameworków do inżynierii wstecznej.| x |
| **8.5** | MSTG-RESILIENCE-5 | Aplikacja wykrywa i reaguje na działanie jej w emulatorze.  | x |
| **8.6** | MSTG-RESILIENCE-6 | Aplikacja wykrywa i reaguje na manipulację kodem i danymi we własnej przestrzeni pamięci. | x |
| **8.7** | MSTG-RESILIENCE-7 | Aplikacja implementuje wiele mechanizmów w każdej kategorii obrony (od 8.1 do 8.6). Zauważ, że niezawodność skaluje się wraz z ilością, różnorodnością oryginalnością zastosowanych mechanizmów. | x |
| **8.8** | MSTG-RESILIENCE-8 | Mechanizmy wykrywania wywołują odpowiedzi różnego typu, w tym reakcje opóźnione i niejawne. | x |
| **8.9** | MSTG-RESILIENCE-9 | Obfuskacja jest stosowana do obrony programowej, która z kolei utrudnia deobfuskację za pomocą analizy dynamicznej.  | x |

### Wiązanie urządzenia (Device Binding)

| # | MSTG-ID | Description | R |
| -- | ----------- | ---------------------- | - |
| **8.10** | MSTG-RESILIENCE-10 | Aplikacja implementuje funkcję „Wiązania Urządzenia” przy użyciu sygnatury urządzenia pochodzącego z wielu właściwości, metadanych unikalnych dla urządzenia. | x |

<!-- \pagebreak -->

### Utrudnianie Zrozumienia

| # | MSTG-ID | Description | R |
| -- | ----------- | ---------------------- | - |
| **8.11** | MSTG-RESILIENCE-11 | Wszystkie pliki wykonywalne i biblioteki należące do aplikacji są szyfrowane na poziomie plików i/lub ważne segmenty kodu i danych wewnątrz plików wykonywalnych są szyfrowane lub pakowane. Trywialna analiza statyczna nie ujawnia ważnego kodu ani danych. | x |
| **8.12** | MSTG-RESILIENCE-12 | Jeśli celem obfuskacji jest ochrona wrażliwych obliczeń, stosuje się schemat obfuskacji, który jest zarówno odpowiedni dla konkretnego zadania, jak i odporny na ręczne i automatyczne metody deobfuskacji, biorąc pod uwagę obecnie opublikowane badania. Skuteczność schematu obfuskacji należy zweryfikować za pomocą testów manualnych. Należy pamiętać, że w miarę możliwości preferowane są funkcje izolacji sprzętowej, a nie obfuskacji. | x |

### Utrudnianie Podsłuchiwania

| # | MSTG-ID | Description | R |
| -- | ----------- | ---------------------- | - |
| **8.13** | MSTG-RESILIENCE-13 | Jako dogłębną ochronę, oprócz solidnego zabezpieczenia stron komunikujących się, można zastosować szyfrowanie payloadu na poziomie aplikacji, aby jeszcze bardziej utrudnić podsłuchiwanie. | x |

<!-- \pagebreak -->

## Bibliografia

Przewodnik testowania zabezpieczeń mobilnych OWASP zawiera szczegółowe instrukcje dotyczące weryfikacji wymagań wymienionych powyżej.

- Android: Testing Resiliency Against Reverse Engineering - <https://github.com/OWASP/owasp-mstg/blob/master/Document/0x05j-Testing-Resiliency-Against-Reverse-Engineering.md>
- iOS: Testing Resiliency Against Reverse Engineering - <https://github.com/OWASP/owasp-mstg/blob/master/Document/0x06j-Testing-Resiliency-Against-Reverse-Engineering.md>

Aby uzyskać więcej informacji, zobacz także:

- OWASP Mobile Top 10: M8 (Code Tampering) - <https://owasp.org/www-project-mobile-top-10/2016-risks/m8-code-tampering>
- OWASP Mobile Top 10: M9 (Reverse Engineering) - <https://owasp.org/www-project-mobile-top-10/2016-risks/m9-reverse-engineering>
- OWASP Reverse Engineering Threats - <https://wiki.owasp.org/index.php/Technical_Risks_of_Reverse_Engineering_and_Unauthorized_Code_Modification>
- OWASP Reverse Engineering and Code Modification Prevention - <https://wiki.owasp.org/index.php/OWASP_Reverse_Engineering_and_Code_Modification_Prevention_Project>
