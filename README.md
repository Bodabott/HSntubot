# HSntubot

from bs4 import BeautifulSoup
import urllib.request as ur
s = ur.urlopen("http://hearthstone.metabomb.net/game-guides/hearthstone-deck-tier-list-02-09-2016")

soup = BeautifulSoup(s.read())

print (soup.prettify())
