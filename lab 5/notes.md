

    1.Происходит перехват сигнала и вызов обработчика (trap 'echo "Аварийное завершение..."; exit 1' SIGINT)

    2.При вызове команды ls -l /proc/self текущим процессом становится процесс ls, а при ls -l /proc/&& происходит вывод информации о текущем процессе

    3.stdin - дескриптор 0 (/dev/pts/1) stdout - дескриптор 1 (/dev/pts/1) stderr - дескриптор 2 (/dev/pts/1)

    4.дексриптор 1 меняется на /tmp/ls.out, дескриптор 2 соответствено на /tmp/ls.err

    5.дескриптор 0 (ввода) соотвестенно изменился

    6.происходит замена текущего процесса (терминала интерпретатора shell) на ps -l, после отработки команды происходит завершение процесса

    7.Что означает pos при выводе содержимого файла /proc/$$/fdinfo/3? Указатель чтения/записи. В примере он равен 14, потому что мы уже записали в файл ~/test.out 13 символов (Test3\nTest333), и сейчас указатель стоит на том, с которого продолжится запись.

    8.Существует ли возможность читать содержимое файла test.out даже после его удаления? Почему так происходит? Возможность есть, так как несмотря на то, что файл удален, он остался связан с дескриптором 4 и через обращение к дескриптору можем прочитать его содержание.
