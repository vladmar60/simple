# simple
# check_website.py

import requests

def check_website(url):
    try:
        response = requests.get(url, timeout=5)
        if response.status_code == 200:
            print(f"✅ {url} is online!")
        else:
            print(f"⚠️ {url} responded with status code: {response.status_code}")
    except requests.exceptions.RequestException:
        print(f"❌ {url} is unreachable.")

if __name__ == "__main__":
    site = input("Enter website URL (e.g., https://example.com): ")
    check_website(site)
