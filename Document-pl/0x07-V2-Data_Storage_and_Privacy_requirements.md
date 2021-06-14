# V2: Przechowywanie Danych i Wymagania Dotyczące Prywatności

## Cele Kontrolne

Ochrona danych wrażliwych, takich jak dane uwierzytelniające użytkownika i informacje prywatne, jest kluczowym elementem bezpieczeństwa urządzeń mobilnych. Po pierwsze, wrażliwe dane mogą zostać przypadkowo ujawnione innym aplikacjom działającym na tym samym urządzeniu, jeśli mechanizmy systemu operacyjnego, takie jak IPC, są wykorzystywane niewłaściwie. Dane mogą również przypadkowo wyciekać do pamięci w chmurze, kopii zapasowych lub pamięci podręcznej klawiatury. Ponadto urządzenia mobilne można łatwiej zgubić lub ukraść w porównaniu z innymi typami urządzeń, więc bardziej prawdopodobnym scenariuszem jest uzyskanie przez przeciwnika fizycznego dostępu. W takim przypadku można wprowadzić dodatkowe zabezpieczenia, aby utrudnić wydobycie wrażliwych danych.

Należy zauważyć, że MASVS jest skoncentrowany na aplikacjach, więc nie obejmuje zasad na poziomie urządzenia, takich jak te wymuszane przez rozwiązania MDM. Zachęcamy do korzystania z takich zasad w kontekście korporacyjnym w celu dalszego zwiększenia bezpieczeństwa danych.

### Definicja Wrażliwych Danych 

Dane wrażliwe w kontekście MASVS dotyczą zarówno danych uwierzytelniających użytkownika, jak i wszelkich innych danych uważanych za wrażliwe w danym kontekście, takich jak:

- Informacje umożliwiające identyfikację osoby (PII), które można wykorzystać do kradzieży tożsamości: numery ubezpieczenia społecznego, numery kart kredytowych, numery kont bankowych, informacje o stanie zdrowia;
- Wysoce wrażliwe dane, których narażenie na szwank może prowadzić do utraty reputacji i/lub kosztów finansowych: Informacje umowne, informacje objęte umowami o zachowaniu poufności, informacje zarządu;
- Wszelkie dane, które muszą być chronione przez prawo lub ze względu na zgodność z ustawami prawnymi.

## Wymagania Dotyczące Weryfikacji Bezpieczeństwa

Zdecydowanej większości problemów z ujawnianiem danych można zapobiec, przestrzegając prostych zasad. Większość kontroli wymienionych w tym rozdziale jest obowiązkowa dla wszystkich poziomów weryfikacji.

| # | MSTG-ID | Description | L1 | L2 |
| -- | ---------- | ---------------------- | - | - |
| **2.1** | MSTG-STORAGE-1 | Systemy przechowywania danych uwierzytelniających muszą być używane do przechowywania poufnych danych, takich jak informacje umożliwiające identyfikację (PII), dane uwierzytelniające użytkownika lub klucze kryptograficzne. | x | x |
| **2.2** | MSTG-STORAGE-2 | Żadne poufne dane nie powinny być przechowywane poza kontenerem aplikacji lub poza systemem przechowywania danych uwierzytelniających.| x | x |
| **2.3** | MSTG-STORAGE-3 | Żadne poufne dane nie są zapisywane w logach aplikacji. | x | x |
| **2.4** | MSTG-STORAGE-4 | Żadne wrażliwe dane nie są udostępniane stronom trzecim, chyba że są one niezbędną częścią architektury. | x | x |
| **2.5** | MSTG-STORAGE-5 | Pamięć podręczna klawiatury jest wyłączona w przypadku wprowadzania tekstu przetwarzającego poufne dane. | x | x |
| **2.6** | MSTG-STORAGE-6 | Żadne wrażliwe dane nie są ujawniane za pośrednictwem mechanizmów IPC. | x | x |
| **2.7** | MSTG-STORAGE-7 | Żadne poufne dane, takie jak hasła lub PINy, nie są ujawniane przez interfejs użytkownika. | x | x |
| **2.8** | MSTG-STORAGE-8 | Kopie zapasowe generowane przez mobilny system operacyjny nie zawierają żadnych wrażliwych danych. |   | x |
| **2.9** | MSTG-STORAGE-9 | Aplikacja usuwa poufne dane z widoków po przeniesieniu do pracy w tle. |  | x |
| **2.10** | MSTG-STORAGE-10 | Aplikacja nie przechowuje w pamięci poufnych danych dłużej niż to konieczne, a pamięć jest czyszczona po użyciu. |  | x |
| **2.11** | MSTG-STORAGE-11 | Aplikacja wymusza minimalne zasady bezpieczeństwa dostępu do urządzenia, takie jak wymaganie od użytkownika ustawienia hasła urządzenia. |  | x |
| **2.12** | MSTG-STORAGE-12 | Aplikacja informuje użytkownika o rodzajach przetwarzanych danych osobowych, a także o najlepszych praktykach w zakresie bezpieczeństwa, których użytkownik powinien przestrzegać podczas korzystania z aplikacji. |  | x |
| **2.13** | MSTG-STORAGE-13 | Żadne wrażliwe dane nie powinny być przechowywane lokalnie na urządzeniu mobilnym. Zamiast tego dane powinny być pobierane ze zdalnego punktu końcowego w razie potrzeby i przechowywane tylko w pamięci. |  | x |
| **2.14** | MSTG-STORAGE-14 | Jeśli poufne dane nadal muszą być przechowywane lokalnie, należy je zaszyfrować przy użyciu klucza pochodzącego ze sprzętowej pamięci masowej, która wymaga uwierzytelniania - np. z TEE (Trusted Execution Environment) |  | x |
| **2.15** | MSTG-STORAGE-15 | Pamięć lokalna aplikacji powinna zostać wyczyszczona po nadmiernej liczbie nieudanych prób uwierzytelnienia. |  | x |

## Bibliografia

Przewodnik testowania zabezpieczeń mobilnych OWASP zawiera szczegółowe instrukcje dotyczące weryfikacji wymagań wymienionych w tej sekcji.

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
