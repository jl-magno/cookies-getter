#!/usr/bin/env python3
# Facebook Cookie Getter
# Developed by JL Magno

import os
import time
import sys
import uuid
import string
import random
import re
from os import system as sm
from sys import platform as pf
from time import sleep as sp

# Try to import required modules
try:
    import requests
    import bs4
    from bs4 import BeautifulSoup
    import rich
    from rich import print as rp
    from rich.panel import Panel as pan
    import httpx
except ModuleNotFoundError:
    sm('pip install requests bs4 rich httpx')
    # Re-import after installation
    import requests
    import bs4
    from bs4 import BeautifulSoup
    import rich
    from rich import print as rp
    from rich.panel import Panel as pan
    import httpx

# Color definitions
class Colors:
    # Rich colors
    R = "[bold red]"
    G = "[bold green]"
    Y = "[bold yellow]"
    B = "[bold blue]"
    M = "[bold magenta]"
    P = "[bold violet]"
    C = "[bold cyan]"
    W = "[bold white]"
    
    # ANSI colors
    r = "\033[1;31m"
    g = "\033[1;32m"
    y = "\033[1;33m"
    b = "\033[1;34m"
    m = "\033[1;35m"
    c = "\033[1;36m"
    w = "\033[1;37m"

def rand_color():
    """Return a random rich color"""
    return random.choice([Colors.R, Colors.G, Colors.Y, Colors.B, Colors.M, Colors.P, Colors.C, Colors.W])

def logo():
    """Display the tool logo"""
    rp(pan(f"""\
{rand_color()}                     
