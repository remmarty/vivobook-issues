# Opis problemu

Po 2 miesiącach bezproblemowego użytkowania zaczęły się pojawiać problemy ze stabilnością działania systemów operacyjnych.

* Windows 10 64-bit: ekrany BSoD (najczęściej  Stop Code: MEMORY_MANAGEMENT).
* Ubuntu 18.04 64-bit: problemy przy wybudzaniu z trybu uśpienia (całkowita utrata interakcji z systemem), zawieszanie sie w losowych momentach (co nigdy sie nie zdarzało)

![memory_management_bsod](screenshots/memory_management_bsod.jpg)
![bad_pool_bsod](screenshots/bad_pool_bsod.jpg)

## Podjęte kroki w celu znalezienia przyczyny problemów

### Windows 10

Zaczałem od wielokrotnego przeprowadzenia testów przy użyciu narzędzia **Windows Memory Diagnostics Tool**, którego wynik w _Dzienniku Zdarzeń_ zawsze sugerował problem o charakterze sprzętowym.

![journal_hardware_errors](screenshots/journal_hardware_errors.jpg)

Inne rekordy o błędach:
![kernel_power_journal](screenshots/kernel_power_journal.jpg)
![unexpected_shutdown_journal](screenshots/unexpected_shutdown_journal.jpg)

Podjąłem **pomyślną** próbę przeinstalowania Windowsa za pomocą _Resetuj ustawienia komputera do stanu początkowego_.
Niestety nie byłem w stanie zainstalować poprawnie wszystkich sterowników pobranych ze strony ASUSa ze względu na nieoczekiwane restarty.

Nastepnie podjąłem **nieudaną** próbę reinstalacji z bootowalnego USB:
![recovery_ramdisk_error](screenshots/recovery_ramdisk_error.jpg)                     

### Ubuntu
(http://manpages.ubuntu.com/manpages/trusty/man8/memtester.8.html)

Nieudane były również kilkukrotne próby przeprowadzenia testów na systemie Ubuntu 18.04 64-bit.
W trakcie działania programu **memtester** cały komputer trwale przestawał reagować w losowych momentach mimo, iż test powtórzony na dużo słabszej jednostce sprzętowej działał bez zarzutu.

### Memtest86
(https://www.memtest86.com, https://www.memtest86.com/technical.htm)

Po zapoznaniu sie z dokumentacją, wypaleniu ISO na pendrive i uruchomieniu go otrzymałem następujące wyniki:
![memtest_full](screenshots/memtest_full.jpg)
![memtest_alternative](screenshots/memtest_alternative.jpg)
