CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

PROJECT(mtr C)

ADD_DEFINITIONS(-I. -DHAVE_CONFIG_H -g -O2 -Wall -Wno-pointer-sign)

ADD_LIBRARY(nutils STATIC net.c dns.c raw.c split.c display.c report.c getopt.c getopt1.c select.c asn.c curses.c)

ADD_EXECUTABLE(mtr mtr.c)
TARGET_LINK_LIBRARIES(mtr nutils m resolv ncurses)

#gcc -DHAVE_CONFIG_H  -I.     -g -O2 -Wall -Wno-pointer-sign -MT mtr.o -MD -MP -MF .deps/mtr.Tpo -c -o mtr.o mtr.c
#mv -f .deps/mtr.Tpo .deps/mtr.Po
#gcc -DHAVE_CONFIG_H  -I.     -g -O2 -Wall -Wno-pointer-sign -MT net.o -MD -MP -MF .deps/net.Tpo -c -o net.o net.c
#mv -f .deps/net.Tpo .deps/net.Po
#gcc -DHAVE_CONFIG_H  -I.     -g -O2 -Wall -Wno-pointer-sign -MT dns.o -MD -MP -MF .deps/dns.Tpo -c -o dns.o dns.c
#mv -f .deps/dns.Tpo .deps/dns.Po
#gcc -DHAVE_CONFIG_H  -I.     -g -O2 -Wall -Wno-pointer-sign -MT raw.o -MD -MP -MF .deps/raw.Tpo -c -o raw.o raw.c
#mv -f .deps/raw.Tpo .deps/raw.Po
#gcc -DHAVE_CONFIG_H  -I.     -g -O2 -Wall -Wno-pointer-sign -MT split.o -MD -MP -MF .deps/split.Tpo -c -o split.o split.c
#mv -f .deps/split.Tpo .deps/split.Po
#gcc -DHAVE_CONFIG_H  -I.     -g -O2 -Wall -Wno-pointer-sign -MT display.o -MD -MP -MF .deps/display.Tpo -c -o display.o display.c
#mv -f .deps/display.Tpo .deps/display.Po
#gcc -DHAVE_CONFIG_H  -I.     -g -O2 -Wall -Wno-pointer-sign -MT report.o -MD -MP -MF .deps/report.Tpo -c -o report.o report.c
#mv -f .deps/report.Tpo .deps/report.Po
#gcc -DHAVE_CONFIG_H  -I.     -g -O2 -Wall -Wno-pointer-sign -MT getopt.o -MD -MP -MF .deps/getopt.Tpo -c -o getopt.o getopt.c
#mv -f .deps/getopt.Tpo .deps/getopt.Po
#gcc -DHAVE_CONFIG_H  -I.     -g -O2 -Wall -Wno-pointer-sign -MT getopt1.o -MD -MP -MF .deps/getopt1.Tpo -c -o getopt1.o getopt1.c
#mv -f .deps/getopt1.Tpo .deps/getopt1.Po
#gcc -DHAVE_CONFIG_H  -I.     -g -O2 -Wall -Wno-pointer-sign -MT select.o -MD -MP -MF .deps/select.Tpo -c -o select.o select.c
#mv -f .deps/select.Tpo .deps/select.Po
#gcc -DHAVE_CONFIG_H  -I.     -g -O2 -Wall -Wno-pointer-sign -MT asn.o -MD -MP -MF .deps/asn.Tpo -c -o asn.o asn.c
#mv -f .deps/asn.Tpo .deps/asn.Po
#gcc -DHAVE_CONFIG_H  -I.     -g -O2 -Wall -Wno-pointer-sign -MT curses.o -MD -MP -MF .deps/curses.Tpo -c -o curses.o curses.c
#mv -f .deps/curses.Tpo .deps/curses.Po
#gcc  -g -O2 -Wall -Wno-pointer-sign  curses.o  -o mtr mtr.o net.o dns.o raw.o split.o display.o report.o getopt.o getopt1.o select.o asn.o   -lresolv -lm -lncurses
