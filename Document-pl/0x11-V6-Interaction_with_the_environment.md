# V6: Wymagania Dotyczące Interakcji z Platformą

## Cele Kontrolne

Kontrole w tej grupie zapewniają, że aplikacja korzysta z interfejsów API platformy i standardowych komponentów w bezpieczny sposób. Ponadto kontrole obejmują komunikację między procesami aplikacji (IPC).

## Wymagania Dotyczące Weryfikacji Bezpieczeństwa

| # | MSTG-ID | Description | L1 | L2 |
| -- | ---------- | ---------------------- | - | - |
| **6.1** | MSTG-PLATFORM-1 | Aplikacja żąda tylko minimalnego zestawu niezbędnych uprawnień. | x | x |
| **6.2** | MSTG-PLATFORM-2 | Wszystkie dane wejściowe ze źródeł zewnętrznych i użytkownika są sprawdzane i w razie potrzeby oczyszczane. Obejmuje to dane otrzymane za pośrednictwem UI, mechanizmów IPC takich jak Intents, niestandardowych URL, oraz ze źródeł sieciowych.| x | x |
| **6.3** | MSTG-PLATFORM-3 | Aplikacja nie eksportuje wrażliwych funkcji za pośrednictwem niestandardowych URL schemes, chyba że te mechanizmy są odpowiednio chronione. | x | x |
| **6.4** | MSTG-PLATFORM-4 | Aplikacja nie eksportuje wrażliwych funkcji za pośrednictwem procesami IPC, chyba że mechanizmy te są odpowiednio chronione. | x | x |
| **6.5** | MSTG-PLATFORM-5 | JavaScript jest wyłączony w WebViews, chyba że jest to wyraźnie wymagane. | x | x |
| **6.6** | MSTG-PLATFORM-6 | WebView są skonfigurowane tak, aby zezwalały tylko na minimalny zestaw obsługiwanych protokołów (najlepiej by wspierał jedynie HTTPS). Potencjalnie niebezpieczne protokoły takie jak: file, tel oraz app-id nie powinny być obsługiwane | x | x |
| **6.7** | MSTG-PLATFORM-7 | Jeśli natywne metody aplikacji są udostępniane dla WebView, sprawdź, czy WebView renderuje jedynie kod JavaScript zawarty w paczce aplikacji. | x | x |
| **6.8** | MSTG-PLATFORM-8 | Deserializacja obiektu, jeśli istnieje, jest implementowana przy użyciu bezpiecznych interfejsów API dla serializacji. | x | x |
| **6.9** | MSTG-PLATFORM-9 | Aplikacja zabezpiecza się przed atakami nakładek ekranowych (screen overlay attacks). (tylko Android) |  | x |
| **6.10** | MSTG-PLATFORM-10 | Pamięć podręczna, zwykła pamięć i załadowane zasoby dla WebView (JavaScript itp.) powinny zostać wyczyszczone przed zniszczeniem WebView. |  | x |
| **6.11** | MSTG-PLATFORM-11 | Sprawdź, czy aplikacja uniemożliwia korzystanie z niestandardowych klawiatur innych firm za każdym razem, gdy wprowadzane są poufne dane (tylko iOS). | | x |

## Bibliografia

Przewodnik testowania zabezpieczeń mobilnych OWASP zawiera szczegółowe instrukcje dotyczące weryfikacji wymagań wymienionych w tej sekcji.

- Android: Testing Platform Interaction - <https://github.com/OWASP/owasp-mstg/blob/master/Document/0x05h-Testing-Platform-Interaction.md>
- iOS: Testing Platform Interaction - <https://github.com/OWASP/owasp-mstg/blob/master/Document/0x06h-Testing-Platform-Interaction.md>

Aby uzyskać więcej informacji, zobacz także:

- OWASP Mobile Top 10: M1 (Improper Platform Usage) - <https://owasp.org/www-project-mobile-top-10/2016-risks/m1-improper-platform-usage>
- OWASP Mobile Top 10: M7 (Poor Code Quality) - <https://owasp.org/www-project-mobile-top-10/2016-risks/m7-client-code-quality>
- CWE 20 (Improper Input Validation) - <https://cwe.mitre.org/data/definitions/20.html>
- CWE 79 (Improper Neutralization of Input During Web Page Generation) - <https://cwe.mitre.org/data/definitions/79.html>
- CWE 200 (Information Leak / Disclosure) - <https://cwe.mitre.org/data/definitions/200.html>
- CWE 250 (Execution with Unnecessary Privileges) - <https://cwe.mitre.org/data/definitions/250.html>
- CWE 672 (Operation on a Resource after Expiration or Release) - <https://cwe.mitre.org/data/definitions/672.html>
- CWE 749 (Exposed Dangerous Method or Function) - <https://cwe.mitre.org/data/definitions/749.html>
- CWE 772 (Missing Release of Resource after Effective Lifetime) - <https://cwe.mitre.org/data/definitions/772.html>
- CWE 920 (Improper Restriction of Power Consumption) - <https://cwe.mitre.org/data/definitions/920.html>
- CWE 925 (Improper Verification of Intent by Broadcast Receiver) - <https://cwe.mitre.org/data/definitions/925.html>
- CWE 926 (Improper Export of Android Application Components) - <https://cwe.mitre.org/data/definitions/926.html>
- CWE 927 (Use of Implicit Intent for Sensitive Communication) - <https://cwe.mitre.org/data/definitions/927.html>
- CWE 939 (Improper Authorization in Handler for Custom URL Scheme) - <https://cwe.mitre.org/data/definitions/939.html>
