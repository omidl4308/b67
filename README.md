# b67
import requests

BASE_RPC = "https://mainnet.base.org"

payload = {
    "jsonrpc": "2.0",
    "method": "eth_blockNumber",
    "params": [],
    "id": 1
}

response = requests.post(BASE_RPC, json=payload)

if response.status_code == 200:
    block = int(response.json()["result"], 16)
    print(f"Latest Base Block: {block}")
else:
    print("Connection failed")
