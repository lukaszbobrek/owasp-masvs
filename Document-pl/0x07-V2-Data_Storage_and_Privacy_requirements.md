# V2: Wymagania dotyczące Przechowywanie Danych i Prywatności

## Cele kontrolne

Ochrona danych wrażliwych, takich jak dane uwierzytelniające oraz informacje poufne jest kluczowym elementem bezpieczeństwa urządzeń mobilnych. Po pierwsze, wrażliwe dane mogą zostać przypadkowo ujawnione innym aplikacjom działającym na tym samym urządzeniu, jeśli mechanizmy systemu operacyjnego, między innymi IPC, są wykorzystywane niewłaściwie. Dane mogą również być nieświadomie udostępniane do pamięci w chmurze, kopii zapasowych lub pamięci podręcznej klawiatury. Ponadto, w porównaniu z innymi typami urządzeń, smartfony są znacznie częściej gubione lub kradzione, co znacznei zwiększa ryzyko uzyskania fizycznego dostępu do urządzenia przez atakującego. Mając do na uwadze, dodatkowe zabezpieczenia mogą zostać wdrożone, w celu utrudnienia dostępu do wrażliwych danych.

Przypominamy, że MASVS opisuje zagadanienia związane z aplikacjami i nie obejmuje rozwiązań możliwych do wdrożenia na poziomie urządzenia, takich jak wdrożenie MDM. Zachęcamy do korzystania z takich rozwiązań w kontekście korporacyjnym, w celu jeszcze lepszego zabezpieczenia danych.

### Definicja Wrażliwych Danych 

Dane wrażliwe w kontekście MASVS dotyczą zarówno danych uwierzytelniających użytkownika, jak i wszelkich innych danych uważanych za poufne w danym kontekście, takich jak:

- Dane umożliwiające identyfikację osoby (PII), które momogą zostać wykorzystane do kradzieży tożsamości: numery dowodów osobistych oraz PESEL, numery kart kredytowych, numery kont bankowych, informacje medyczne;
- Wysoce wrażliwe dane, których ujawnienie może prowadzić do utraty reputacji i/lub kosztów finansowych: Umowy prawne oraz finansowe, informacje objęte umowami o zachowaniu poufności, informacje biznesowe;
- Wszelkie dane, które muszą być chronione przez prawo lub ze względu na zgodność z wymogami prawnymi.

## Wymagania Dotyczące Weryfikacji Bezpieczeństwa

Zdecydowanej większości problemów dotyczących ujawnienia danych można zapobiec przestrzegając kilku prostych zasad. Większość wymogów wymienionych w niniejszym rozdziale jest obowiązkowa dla wszystkich poziomów weryfikacji.

| # | MSTG-ID | Opis | L1 | L2 |
| -- | ---------- | ---------------------- | - | - |
| **2.1** | MSTG-STORAGE-1 | Dedykowane mechanizmy systemowe do przechowywania sekretów muszą być użyte do przechowywania danych wrażliwych, takich jak informacje umożliwiające identyfikację osoby (PII), dane uwierzytelniające lub klucze kryptograficzne. | x | x |
| **2.2** | MSTG-STORAGE-2 | Dane wrażline nie powinny być przechowywane poza kontenerem aplikacji lub  dedykowaną przestrzenią w systemie operacyjnym | x | x |
| **2.3** | MSTG-STORAGE-3 | Dane wrażline nie są zapisywane w logach aplikacji. | x | x |
| **2.4** | MSTG-STORAGE-4 | Dane wrażline nie są udostępniane stronom trzecim, chyba że jest to niezbędne z punktu działania aplikacji. | x | x |
| **2.5** | MSTG-STORAGE-5 | Dane wrażline nie są zapisywane do pamięci podręcznej klawiatury. | x | x |
| **2.6** | MSTG-STORAGE-6 | Dane wrażline nie są ujawniane za pośrednictwem mechanizmów IPC. | x | x |
| **2.7** | MSTG-STORAGE-7 | Dane wrażliwe, takie jak hasła lub kody PIN, nie są ujawniane przez interfejs użytkownika. | x | x |
| **2.8** | MSTG-STORAGE-8 | Kopie zapasowe generowane przez system operacyjny nie zawierają żadnych wrażliwych danych. |   | x |
| **2.9** | MSTG-STORAGE-9 | Aplikacja usuwa dane wrażliwe z zrzutów ekranów wykonywanych w trakcie przejścia aplikacji w tło. |  | x |
| **2.10** | MSTG-STORAGE-10 | Aplikacja nie przechowuje w pamięci poufnych danych dłużej niż jest to konieczne, pamięć powinna być czyszczona od razu po ich wykorzystaniu. |  | x |
| **2.11** | MSTG-STORAGE-11 | Aplikacja weryfikuje czy urządzenie jest zabezpieczeone przed anonimowym dostępem, na przykład poprzez kod PIN lub biometrię. |  | x |
| **2.12** | MSTG-STORAGE-12 | Aplikacja informuje użytkownika o sposobie przetwarzania danych osobowych, a także o najlepszych praktykach w zakresie bezpieczeństwa, których użytkownik powinien przestrzegać podczas korzystania z aplikacji. |  | x |
| **2.13** | MSTG-STORAGE-13 | Dane wrażliwe nie powinny być przechowywane lokalnie na urządzeniu mobilnym. Zamiast tego, niezbędne dane powinny być pobierane z serwera i przechowywane wyłącznie w pamięci. |  | x |
| **2.14** | MSTG-STORAGE-14 | Jeśli poufne dane muszą być przechowywane lokalnie, powinny być zaszyfrowane przy użyciu kluczy pochodzących z dedykowanego koprocesora, odseparowanego sprzętowo od systemu operacyjnego (KeyStore lub KeyChain). Operacje kryptograficzne muszą odbywać się w bezpiecznym środowisku TEE (ang. Trusted Execution Environment). | x |
| **2.15** | MSTG-STORAGE-15 | Pamięć lokalna aplikacji powinna zostać wyczyszczona po nadmiernej liczbie nieudanych prób uwierzytelnienia. |  | x |

## Bibliografia

OWASP MSTG zawiera szczegółowe instrukcje dotyczące weryfikacji wymagań wymienionych w tej sekcji.

- Android: Testing Data Storage - <https://github.com/OWASP/owasp-mstg/blob/master/Document/0x05d-Testing-Data-Storage.md>
- iOS: Testing Data Storage - <https://github.com/OWASP/owasp-mstg/blob/master/Document/0x06d-Testing-Data-Storage.md>

Aby uzyskać więcej informacji, zobacz także:

- OWASP Mobile Top 10: M1 (Improper Platform Usage) - <https://owasp.org/www-project-mobile-top-10/2016-risks/m1-improper-platform-usage>
- OWASP Mobile Top 10: M2 (Insecure Data Storage) - <https://owasp.org/www-project-mobile-top-10/2016-risks/m2-insecure-data-storage>
- CWE 117 (Improper Output Neutralization for Logs) - <https://cwe.mitre.org/data/definitions/117.html>
- CWE 200 (Information Exposure) - <https://cwe.mitre.org/data/definitions/200.html>
- CWE 276 (Incorrect Default Permissions) - <https://cwe.mitre.org/data/definitions/276.html>
- CWE 311 (Missing Encryption of Sensitive Data) - <https://cwe.mitre.org/data/definitions/311.html>
- CWE 312 (Cleartext Storage of Sensitive Information) - <https://cwe.mitre.org/data/definitions/312.html>
- CWE 316 (Cleartext Storage of Sensitive Information in Memory) - <https://cwe.mitre.org/data/definitions/316.html>
- CWE 359 (Exposure of Private Information ('Privacy Violation')) - <https://cwe.mitre.org/data/definitions/359.html>
- CWE 522 (Insufficiently Protected Credentials) - <https://cwe.mitre.org/data/definitions/522.html>
- CWE 524 (Information Exposure Through Caching) - <https://cwe.mitre.org/data/definitions/524.html>
- CWE 530 (Exposure of Backup File to an Unauthorized Control Sphere) - <https://cwe.mitre.org/data/definitions/530.html>
- CWE 532 (Information Exposure Through Log Files) - <https://cwe.mitre.org/data/definitions/532.html>
- CWE 534 (Information Exposure Through Debug Log Files) - <https://cwe.mitre.org/data/definitions/534.html>
- CWE 634 (Weaknesses that Affect System Processes) - <https://cwe.mitre.org/data/definitions/634.html>
- CWE 798 (Use of Hard-coded Credentials) - <https://cwe.mitre.org/data/definitions/798.html>
- CWE 921 (Storage of Sensitive Data in a Mechanism without Access Control) - <https://cwe.mitre.org/data/definitions/921.html>
- CWE 922 (Insecure Storage of Sensitive Information) - <https://cwe.mitre.org/data/definitions/922.html>
