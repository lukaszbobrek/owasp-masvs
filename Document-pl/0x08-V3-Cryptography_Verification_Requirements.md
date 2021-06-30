# V3: Wymagania dotyczące Kryptografii

## Cele kontrolne

Kryptografia jest niezbędnym elementem ochrony danych przechowywanych na urządzeniu mobilnym. Jest to kategoria, w której potencjalne błędy mogą mieć bardzo duży wpływ na bezpieczństwo aplikacji, w szczególności kiedy nie są zachowane odpowiednie standardy. Celem sprawdzeń w tym rozdziale jest potwierdzenie, że aplikacja korzysta z kryptografii zgodnie z najlepszymi praktykami branżowymi, w tym:
- Korzysta ze sprawdzonych bibliotek kryptograficznych;
- Wybrano właściwe moduły kryptograficzne dla odpowiednich zastosowań,
- Korzysta z generatorów liczb losowych gwarantujących wymaganą losowość tam gdzie jest to wymagane. 
- 
## Wymagania Dotyczące Weryfikacji Bezpieczeństwa

| # | MSTG-ID | Opis | L1 | L2 |
| -- | ---------- | ---------------------- | - | - |
| **3.1** | MSTG-CRYPTO-1 | Aplikacja nie korzysta wyłącznie z kryptografii symetrycznej z kluczami umieszczonymi w kodzie źródłowym.| x | x |
| **3.2** | MSTG-CRYPTO-2 | Aplikacja korzysta wyłącznie ze sprawdzonych oraz uznawanych za bezpieczne modułów kryptograficznych. | x | x |
| **3.3** | MSTG-CRYPTO-3 | Aplikacja używa modułów kryptograficznych, które są właściwe dla konkretnego przypadku użycia oraz skonfigurowane zgodnymi z najlepszymi praktykami branżowymi. | x | x |
| **3.4** | MSTG-CRYPTO-4 | Aplikacja nie korzysta z protokołów ani algorytmów kryptograficznych, które są powszechnie uważane za przestarzałe pod względem bezpieczeństwa. | x | x |
| **3.5** | MSTG-CRYPTO-5 | Aplikacja nie wykorzystuje wielokrotnie tego samego klucza kryptograficznego do wielu celów. | x | x |
| **3.6** | MSTG-CRYPTO-6 | Wszystkie wartości losowe są generowane przy użyciu generatorów liczb losowych gwarantujących wymaganą losowość. | x | x |

## Bibliografia

Przewodnik testowania zabezpieczeń mobilnych OWASP zawiera szczegółowe instrukcje dotyczące weryfikacji wymagań wymienionych w tej sekcji.

- Android: Testing Cryptography - <https://github.com/OWASP/owasp-mstg/blob/master/Document/0x05e-Testing-Cryptography.md>
- iOS: Testing Cryptography - <https://github.com/OWASP/owasp-mstg/blob/master/Document/0x06e-Testing-Cryptography.md>

Aby uzyskać więcej informacji, zobacz także:

- OWASP Mobile Top 10: M5 (Insufficient Cryptography) - <https://owasp.org/www-project-mobile-top-10/2016-risks/m5-insufficient-cryptography>
- CWE 310 (Cryptographic Issues) - <https://cwe.mitre.org/data/definitions/310.html>
- CWE 321 (Use of Hard-coded Cryptographic Key) - <https://cwe.mitre.org/data/definitions/321.html>
- CWE 326 (Inadequate Encryption Strength) - <https://cwe.mitre.org/data/definitions/326.html>
- CWE 327 (Use of a Broken or Risky Cryptographic Algorithm) - <https://cwe.mitre.org/data/definitions/327.html>
- CWE 329 (Not Using a Random IV with CBC Mode) - <https://cwe.mitre.org/data/definitions/329.html>
- CWE 330 (Use of Insufficiently Random Values) - <https://cwe.mitre.org/data/definitions/330.html>
- CWE 337 (Predictable Seed in PRNG) - <https://cwe.mitre.org/data/definitions/337.html>
- CWE 338 (Use of Cryptographically Weak Pseudo Random Number Generator (PRNG)) - <https://cwe.mitre.org/data/definitions/338.html>
