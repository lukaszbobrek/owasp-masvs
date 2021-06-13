# V1: Wymagania Architektury, Projektowania and Modelowania Zagrożeń 

## Cel Kontroli

W idealnym świecie bezpieczeństwo byłoby brane pod uwagę we wszystkich fazach rozwoju. W rzeczywistości jednak bezpieczeństwo jest często rozważane tylko na późnym etapie SDLC. Oprócz kontroli technicznych, MASVS wymaga istnienia procesów zapewniających, że bezpieczeństwo zostało wyraźnie uwzględnione podczas planowania architektury aplikacji mobilnej oraz że znane są role funkcjonalne i bezpieczeństwa wszystkich komponentów. Ponieważ większość aplikacji mobilnych pełni rolę klientów usług zdalnych, należy zadbać o to, aby również w stosunku do tych usług stosowane były odpowiednie standardy bezpieczeństwa – testowanie aplikacji mobilnej w izolacji nie jest wystarczające.

Kategoria „V1” zawiera wymagania dotyczące architektury i projektu aplikacji. Jest więc to jedyna kategoria, która nie odnosi się do technicznych przypadków testowych w OWASP Mobile Testing Guide. Aby omówić takie tematy, jak modelowanie zagrożeń, bezpieczne SDLC lub zarządzanie kluczami, użytkownicy MASVS powinni zapoznać się z odpowiednimi projektami OWASP i/lub innymi standardami, takimi jak te, do których linki znajdują się poniżej.

## Security Verification Requirements

The requirements for MASVS-L1 and MASVS-L2 are listed below.

| # | MSTG-ID | Description | L1 | L2 |
| -- | ---------- | ---------------------- | - | - |
| **1.1** | MSTG-ARCH-1 | Wszystkie komponenty aplikacji są rozpoznane i wiadomo, że są potrzebne . | x | x |
| **1.2** | MSTG-ARCH-2 | Kontrole bezpieczeństwa nigdy nie są wymuszane tylko po stronie klienckiej, ale na odpowiednich zdalnych punktach końcowych | x | x |
| **1.3** | MSTG-ARCH-3 | Zdefiniowano architekturę wysokiego poziomu dla aplikacji mobilnej i wszystkich podłączonych usług zdalnych, w której zajęto się bezpieczeństwem | x | x |
| **1.4** | MSTG-ARCH-4 | Dane uważane za wrażliwe w kontekście aplikacji mobilnej są wyraźnie zidentyfikowane | x | x |
| **1.5** | MSTG-ARCH-5 | Wszystkie komponenty aplikacji są zdefiniowane pod kątem funkcji biznesowych i/lub funkcji bezpieczeństwa, które zapewniają |  | x |
| **1.6** | MSTG-ARCH-6 | Opracowano model zagrożeń dla aplikacji mobilnej i powiązanych usług zdalnych, który identyfikuje potencjalne zagrożenia i środki zaradcze |  | x |
| **1.7** | MSTG-ARCH-7 | Wszystkie kontrole bezpieczeństwa mają scentralizowaną implementacje |  | x |
| **1.8** | MSTG-ARCH-8 | Istnieje wyraźna polityka dotycząca zarządzania kluczami kryptograficznymi (jeśli istnieją) oraz wymuszany jest cykl życia kluczy kryptograficznych. Idealnie, postępuj zgodnie ze standardem zarządzania kluczami, takim jak NIST SP 800-57. |  | x |
| **1.9** | MSTG-ARCH-9 | Istnieje mechanizm wymuszania aktualizacji aplikacji mobilnej. |  | x |
| **1.10** | MSTG-ARCH-10 | Bezpieczeństwo dotyczy wszystkich ciągłych cykli rozwoju oprogramowania |  | x |
| **1.11** | MSTG-ARCH-11 | Istnieje Polityka Odpowiedzialnego Ujawniania Podatności (VDP) i jest skutecznie stosowana |  | x |
| **1.12** | MSTG-ARCH-12 | Aplikacja powinna być zgodna z przepisami i regulacjami dotyczącymi prywatności. | x | x |

## Bibliografia

Aby uzyskać więcej informacji, zobacz także:

- OWASP Mobile Top 10: M10 (Extraneous Functionality) - <https://owasp.org/www-project-mobile-top-10/2016-risks/m10-extraneous-functionality>
- OWASP Threat modelling - <https://owasp.org/www-community/Application_Threat_Modeling>
- OWASP Secure SDLC Cheat Sheet - <https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets_excluded/Secure_SDLC_Cheat_Sheet.md>
- Microsoft SDL - <https://www.microsoft.com/en-us/sdl/>
- NIST SP 800-57 - <https://csrc.nist.gov/publications/detail/sp/800-57-part-1/rev-5/final>
- security.txt - <https://securitytxt.org/>
