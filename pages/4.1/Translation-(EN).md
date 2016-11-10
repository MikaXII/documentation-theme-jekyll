---
layout: page
title: Translation (EN)
wikiPageName: Translation-(EN)
menu: wiki
---

Recalbox is not available for you language ? Translate it is easy and require no technical skill.

# The easy way
Join us on [POEditor recalbox project](https://poeditor.com/join/project/hEp5Khj4Ck) to edit exsting translation or add you native language !

# Status
check the status of your language in recalbox : http://archive.recalbox.com/4/rpi2/unstable/last/potstats.html.

# Translate
## Introduction
To translate Recalbox, you have to write a file giving all the conversions (to answer to the question "How to you say ... into your language ?"). This file is called a po file. Then, there is a fr.po for the french translation, a es.po, a ru.po, ... one for each language. A .po file is a simple text file where you can associate to each msgid (message identifier) a msgstr (message string). You can open it with any text editor, however, poedit for windows or lokalize (kbabel) for linux will help you to translate.

Example :

<pre>
# GuiMenu.cpp:900
msgid "CONFIGURE A CONTROLLER"
msgstr ""
</pre>

becomes for the french translation

<pre>
# GuiMenu.cpp:900
msgid "CONFIGURE A CONTROLLER"
msgstr "CONFIGURER UNE MANETTE"
</pre>

Lines starting by a # are ignored. 

## Get the .pot file (po template file)

Get the template pot file at https://raw.githubusercontent.com/recalbox/recalbox-emulationstation/recalbox-buildroot/locale/emulationstation2.pot

You can update an existing translation too by taking the current po here : https://github.com/recalbox/recalbox-emulationstation/tree/recalbox-buildroot/locale/lang

## Send us your file

Send your po file via a github pr, or contact us via the irc link on top of recalbox.com.

# Advanced information
## What's %i ?
Some text to translate contains %i strings. It's when a number is required. For example, 1 player, 2 players, ... Keep this symbol in the translated string.

Example :
<pre>
msgid "INPUT %i"
msgstr "JOUEUR %i"
</pre>

## What's plural forms ?
English has 2 plural forms. Singular and plural. In most of languages, this is not the case, or the formula is different. For example, in english, plural is when there are 0 or more than 1 items. Singular is when there is exactly 1 item. In french, singular is 0 and 1 and the rest is plural. Some languages have up to 7 plural forms. You don't have to provide the formula. (it can be found on internet on sites like http://localization-guide.readthedocs.org/en/latest/l10n/pluralforms.html)

However, when you translated, you've to specify each plural form.

Example :
<pre>
msgid "%i GAME AVAILABLE"
msgid_plural "%i GAMES AVAILABLE"
msgstr[0] "%i JEU DISPONIBLE"
msgstr[1] "%i JEUX DISPONIBLES"
</pre>

The line 1 and 2 indicate the 2 english forms. The other lines are for your plural forms. For the french, there are two lines, singular and plural, but there can have many lines depending on your language.

## What's #fuzzy ?
fuzzy means that gettext tried to translate by itself. It's generally not good at all. Automatic translation is done mainly when there was an error in the original english text.

Example :
<pre>
#, fuzzy
msgid "CANCEL"
msgstr "ANNULER"
</pre>

must be changed by removing the fuzzy comment to become

<pre>
msgid "CANCEL"
msgstr "ANNULER"
</pre>

## What's #~ ?
What's the last lines at the end of the .po starting by #~

You can remove these lines. It's the translations which don't exist anymore in Recalbox and have been automatically commented.
Example :

<pre>
#~ msgid "DEFAULT"
#~ msgstr "PAR DÉFAUT"
</pre>

## Need help ?
If you need any help or want to propose your .po, contact us on irc (link at the top of recalbox.com)

## Command line commands
To see untranslated messages, just run

<pre>
msgattrib --untranslated fr_FR.po
msgattrib --fuzzy fr_FR.po
</pre>

## Developpers: add a new language in Recalbox
* recalbox-buildroot : add the language in BR2_GENERATE_LOCALE and BR2_ENABLE_LOCALE_WHITELIST
* recalbox-emulationstation: add the new directory in locale/lang, copy the .pot into it, and rerun cmake .
* recalbox-emulationstation: add the item choice in MainMenu.cpp 
