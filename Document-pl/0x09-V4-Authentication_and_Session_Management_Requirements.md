# V4: Wymagania Dotyczące Uwierzytelniania i Zarządzania Sesją

## Cele Kontrolne

W większości przypadków użytkownicy logujący się do usługi zdalnej są integralną częścią ogólnej architektury aplikacji mobilnej. Mimo że większość logiki dzieje się w punkcie końcowym, MASVS określa pewne podstawowe wymagania dotyczące sposobu zarządzania kontami użytkowników i sesjami.

## Wymagania Dotyczące Weryfikacji Bezpieczeństwa

| # | MSTG-ID | Opis | L1 | L2 |
| -- | ---------- | ---------------------- | - | - |
| **4.1** | MSTG-AUTH-1 | Jeśli aplikacja zapewnia użytkownikom dostęp do usługi zdalnej, to na serwerze jest wykonywana forma uwierzytelniania - na przykład uwierzytelnienie nazwą użytkownika oraz hasłem. | x | x |
| **4.2** | MSTG-AUTH-2 | Jeśli używane jest stanowe zarządzanie sesjami, to serwer używa losowo wygenerowanych identyfikatorów sesji w celu uwierzytelniania żądań klientów bez wysyłania poświadczeń użytkownika. | x | x |
| **4.3** | MSTG-AUTH-3 | Jeśli używane jest uwierzytelnianie bezstanowe oparte na tokenach, to serwer udostępnia token, który został podpisany przy użyciu bezpiecznego algorytmu. | x | x |
| **4.4** | MSTG-AUTH-4 | Po stronie serwerowej unieważniana jest istniejąca sesja, gdy użytkownik się wyloguje. | x | x |
| **4.5** | MSTG-AUTH-5 | Polityka haseł istnieje i jest weryfikowana na serwerze. | x | x |
| **4.6** | MSTG-AUTH-6 | Serwer implementuje mechanizm ochrony przed przesyłaniem danych logowania zbyt wiele razy. | x | x |
| **4.7** | MSTG-AUTH-7 | Sesje są unieważniane na serwerze po wstępnie zdefiniowanym okresie nieaktywności, a tokeny dostępu wygasają. | x | x |
| **4.8** | MSTG-AUTH-8 | Uwierzytelnianie biometryczne, jeśli istnieje, to opiera się na odblokowaniu keychain/keystore. | | x |
| **4.9** | MSTG-AUTH-9 | Drugi czynnik uwierzytelniania istnieje na serwerze i wymaganie dotyczące 2FA jest konsekwentnie egzekwowane.  | | x |
| **4.10** | MSTG-AUTH-10 | Poufne transakcje wymagają uwierzytelniania wielo-etapowego. | | x |
| **4.11** | MSTG-AUTH-11 | Aplikacja informuje użytkownika o wszystkich wrażliwych działaniach na jego koncie. Użytkownicy mogą przeglądać listę urządzeń, przeglądać informacje kontekstowe (adres IP, lokalizacja itp.) oraz blokować określone urządzenia. | | x |
| **4.12** | MSTG-AUTH-12 | Modele autoryzacji powinny być zdefiniowane i wymuszane na serwerze. | x | x |

## Bibliografia

Przewodnik testowania zabezpieczeń mobilnych OWASP zawiera szczegółowe instrukcje dotyczące weryfikacji wymagań wymienionych w tej sekcji.

- General: Authentication and Session Management - <https://github.com/OWASP/owasp-mstg/blob/master/Document/0x04e-Testing-Authentication-and-Session-Management.md>
- Android: Testing Local Authentication - <https://github.com/OWASP/owasp-mstg/blob/master/Document/0x05f-Testing-Local-Authentication.md>
- iOS: Testing Local Authentication - <https://github.com/OWASP/owasp-mstg/blob/master/Document/0x06f-Testing-Local-Authentication.md>

Aby uzyskać więcej informacji, zobacz także:

- OWASP Mobile Top 10: M4 (Insecure Authentication) - <https://owasp.org/www-project-mobile-top-10/2016-risks/m4-insecure-authentication>
- OWASP Mobile Top 10: M6 (Insecure Authorization) - <https://owasp.org/www-project-mobile-top-10/2016-risks/m6-insecure-authorization>
- CWE 287 (Improper Authentication) - <https://cwe.mitre.org/data/definitions/287.html>
- CWE 307 (Improper Restriction of Excessive Authentication Attempts) - <https://cwe.mitre.org/data/definitions/307.html>
- CWE 308 (Use of Single-factor Authentication) - <https://cwe.mitre.org/data/definitions/308.html>
- CWE 521 (Weak Password Requirements) - <https://cwe.mitre.org/data/definitions/521.html>
- CWE 604 (Use of Client-Side Authentication) - <https://cwe.mitre.org/data/definitions/604.html>
- CWE 613 (Insufficient Session Expiration) - <https://cwe.mitre.org/data/definitions/613.html>
