# V7: Wymagania Dotyczące Jakości Kodu i Ustanawianiu Architektury

## Cele Kontrolne

Celem tej kontroli jest zapewnienie, że podczas tworzenia aplikacji przestrzegane są podstawowe praktyki bezpiecznego kodowania  oraz że „bezpłatne” funkcje bezpieczeństwa oferowane przez kompilator są używane.

## Wymagania Dotyczące Weryfikacji Bezpieczeństwa

| # | MSTG-ID | Opis | L1 | L2 |
| -- | ---------- | ---------------------- | - | - |
| **7.1** | MSTG-CODE-1 |Aplikacja jest podpisana i zaopatrzona w ważny certyfikat, którego klucz prywatny jest odpowiednio chroniony.| x | x |
| **7.2** | MSTG-CODE-2 | Aplikacja została zbudowana w celu wydania, z ustawieniami kompilacyjnymi odpowiednimi dla  wydania (np. bez możliwości debugowania). | x | x |
| **7.3** | MSTG-CODE-3 | Symbole do debugowania zostały usunięte z natywnych plików binarnych. | x | x |
| **7.4** | MSTG-CODE-4 | Kod do debugowania i kod dla pomocy programiście (np. kod testowy, backdoory, ukryte ustawienia) zostały usunięte. Aplikacja nie zapisuje pełnych błędów ani komunikatów debugowania. | x | x |
| **7.5** | MSTG-CODE-5 | Wszystkie komponenty stron trzecich używane przez aplikację mobilną, takie jak biblioteki i frameworki, są identyfikowane i sprawdzane pod kątem znanych podatności bezpieczeństwa. | x | x |
| **7.6** | MSTG-CODE-6 | Aplikacja przechwytuje i obsługuje możliwe wyjątki.| x | x |
| **7.7** | MSTG-CODE-7 | Logika obsługi błędów w kontrolach bezpieczeństwa domyślnie odmawia dostępu. | x | x |
| **7.8** | MSTG-CODE-8 | W kodzie niezarządzanym (unmanaged) pamięć jest przydzielana, czyszczona i używana w bezpieczny sposób.  | x | x |
| **7.9** | MSTG-CODE-9 | Używane są bezpłatne funkcjonalności bezpieczeństwa oferowane przez toolchain, takie jak minimalizacja kodu bajtowego, ochrona stosu, obsługa PIE i automatyczne zliczanie referencji. | x | x |

## Bibliografia

Przewodnik testowania zabezpieczeń mobilnych OWASP zawiera szczegółowe instrukcje dotyczące weryfikacji wymagań wymienionych powyżej.

- Android: Testing Code Quality and Build Settings - <https://github.com/OWASP/owasp-mstg/blob/master/Document/0x05i-Testing-Code-Quality-and-Build-Settings.md>
- iOS: Testing Code Quality and Build Settings - <https://github.com/OWASP/owasp-mstg/blob/master/Document/0x06i-Testing-Code-Quality-and-Build-Settings.md>

Aby uzyskać więcej informacji, zobacz także:

- OWASP Mobile Top 10: M7 (Poor Code Quality) - <https://owasp.org/www-project-mobile-top-10/2016-risks/m7-client-code-quality>
- CWE 20 (Improper Input Validation) - <https://cwe.mitre.org/data/definitions/20.html>
- CWE 89 (Improper Neutralization of Special Elements used in an SQL Command) - <https://cwe.mitre.org/data/definitions/89.html>
- CWE 95 (Improper Neutralization of Directives in Dynamically Evaluated Code ('Eval Injection')) - <https://cwe.mitre.org/data/definitions/95.html>
- CWE 119 (Improper Restriction of Operations within the Bounds of a Memory Buffer) - <https://cwe.mitre.org/data/definitions/119.html>
- CWE 215 (Information Exposure through Debug Information) - <https://cwe.mitre.org/data/definitions/215.html>
- CWE 388 (7PK - Errors) - <https://cwe.mitre.org/data/definitions/388.html>
- CWE 489 (Leftover Debug Code) - <https://cwe.mitre.org/data/definitions/489.html>
- CWE 502 (Deserialization of Untrusted Data) - <https://cwe.mitre.org/data/definitions/502.html>
- CWE 511 (Logic/Time Bomb) - <https://cwe.mitre.org/data/definitions/511.html>
- CWE 656 (Reliance on Security through Obscurity) - <https://cwe.mitre.org/data/definitions/656.html>
- CWE 676 (Use of Potentially Dangerous Function)  - <https://cwe.mitre.org/data/definitions/676.html>
- CWE 937 (OWASP Top Ten 2013 Category A9 - Using Components with Known Vulnerabilities) - <https://cwe.mitre.org/data/definitions/937.html>
