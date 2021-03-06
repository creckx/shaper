Shaper
======

It's pretty simple to use. All you need is IMQ modul in kernel and four imqX devices. Everything else will manage this script.

Instalation
-----------

    # pip install https://github.com/creckx/shaper/archive/master.zip

Usage
-----

    shaper init rate <RATE> ceil <CEIL> iface <IFACE>
    shaper rule add parent <NAME> name <NAME> rate <RATE> ceil <CEIL>
    shaper rule add parent <NAME> name <NAME> rate <RATE> ceil <CEIL> ip <IP>
    shaper rule del name <NAME>
    shaper commit
    shaper list
    shaper help

    Units: bps,kbps,mbps,bit,kbit,mbit
    IP: regular IPv4 with or without (default /32) mask, regular IPv6 with or without prefix (default /128)
    NAME: without spaces and special characters

    init - initialize shaper
    commit - generate scripts and execute them (remove all rules and make new ones)
    list - show your rules in tree

    Beside that you need:
        * Interfaces imq0(down) imq1(up) imq2(down) imq3(up)

    Exit statuses
        0 - everything is ok
        1 - shaper is not initialized, nothing to save, use init command
        2 - caught exception, state is saved
        3 - error during script execution, state is not saved


Developed for EXPERIA GROUP s.r.o. http://www.experia.cz/