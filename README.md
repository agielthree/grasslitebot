# grasslitebot
grasslitebot getgrass farming
buka liteproxy.py 
ubah bagian user id paling bawah
# Main function for reading proxies and starting connections
async def main():
    _user_id = "xxxxxxxxxxxxxxxxxxxxxxxx"
    with open('local_proxies.txt', 'r') as file:
        local_proxies = file.read().splitlines()
    tasks = [asyncio.ensure_future(connect_to_ws(i, _user_id)) for i in local_proxies]
    await asyncio.gather(*tasks)


RUN: 
python3 -m venv venv
. venv/bin/activate
pip install -r requirements.txt
python3 lite_proxy.py
