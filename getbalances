#!/usr/bin/env python3
#BINANCE
import urllib.parse,  urllib.request
from urllib.parse import urljoin, urlencode
import json, hashlib, hmac, time
from datetime import datetime
import requests

BASE_URL = 'https://api.binance.com'
apiKey = ‘YOUR KEY’
secret = ‘YOUR SECRET’

def getBalances():
    PATH = '/api/v3/account'
    timestamp = int(time.time() * 1000)
    headers = {
        'X-MBX-APIKEY': apiKey
    }
    params = {
        'recvWindow': 5000,
        'timestamp': timestamp
    }
    query_string = urllib.parse.urlencode(params)
    params['signature'] = hmac.new(secret.encode('utf-8'), query_string.encode('utf-8'), hashlib.sha256).hexdigest()
    url = urljoin(BASE_URL, PATH)
    print (url)
    r = requests.get(url, headers=headers, params=params)
    dataSet = r.json()
    print (dataSet)


getBalances()
