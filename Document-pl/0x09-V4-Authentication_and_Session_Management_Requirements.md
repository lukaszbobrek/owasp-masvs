# V4: Wymagania Dotyczące Uwierzytelniania i Zarządzania Sesją

## Cele Kontrolne

W większości przypadków użytkownicy logujący się do usługi zdalnej są integralną częścią ogólnej architektury aplikacji mobilnej. Mimo że większość logiki dzieje się w punkcie końcowym, MASVS określa pewne podstawowe wymagania dotyczące sposobu zarządzania kontami użytkowników i sesjami.

## Wymagania Dotyczące Weryfikacji Bezpieczeństwa

| # | MSTG-ID | Description | L1 | L2 |
| -- | ---------- | ---------------------- | - | - |
| **4.1** | MSTG-AUTH-1 | Jeśli aplikacja zapewnia użytkownikom dostęp do usługi zdalnej, w zdalnym punkcie końcowym jest wykonywana pewna forma uwierzytelniania, taka jak uwierzytelnianie nazwą użytkownika/hasłem. | x | x |
| **4.2** | MSTG-AUTH-2 | Jeśli używane jest stanowe zarządzanie sesjami, zdalny punkt końcowy używa losowo wygenerowanych identyfikatorów sesji do uwierzytelniania żądań klientów bez wysyłania poświadczeń użytkownika. | x | x |
| **4.3** | MSTG-AUTH-3 | Jeśli używane jest uwierzytelnianie bezstanowe oparte na tokenach, serwer udostępnia token, który został podpisany przy użyciu bezpiecznego algorytmu. | x | x |
| **4.4** | MSTG-AUTH-4 | Zdalny punkt końcowy kończy istniejącą sesję, gdy użytkownik się wyloguje. | x | x |
| **4.5** | MSTG-AUTH-5 | Polityka haseł istnieje i jest wymuszana na zdalnym punkcie końcowym. | x | x |
| **4.6** | MSTG-AUTH-6 | Zdalny punkt końcowy implementuje mechanizm ochrony przed przesyłaniem danych logowania zbyt wiele razy. | x | x |
| **4.7** | MSTG-AUTH-7 | Sesje są unieważniane na zdalnym punkcie końcowym po wstępnie zdefiniowanym okresie nieaktywności, a tokeny dostępu wygasają. | x | x |
| **4.8** | MSTG-AUTH-8 | Uwierzytelnianie biometryczne, jeśli istnieje, nie jest powiązane ze zdarzeniami (tj. przy użyciu interfejsu API, który po prostu zwraca „prawda” lub „fałsz”). Zamiast tego opiera się na odblokowaniu keychain/keystore. | | x |
| **4.9** | MSTG-AUTH-9 | Drugi czynnik uwierzytelniania istnieje w zdalnym punkcie końcowym i wymaganie 2FA jest konsekwentnie egzekwowane.  | | x |
| **4.10** | MSTG-AUTH-10 | Poufne transakcje wymagają uwierzytelniania krokowego. | | x |
| **4.11** | MSTG-AUTH-11 | Aplikacja informuje użytkownika o wszystkich wrażliwych działaniach na jego koncie. Użytkownicy mogą przeglądać listę urządzeń, przeglądać informacje kontekstowe (adres IP, lokalizacja itp.) oraz blokować określone urządzenia. | | x |
| **4.12** | MSTG-AUTH-12 | Modele autoryzacji powinny być zdefiniowane i wymuszane w zdalnym punkcie końcowym. | x | x |

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
