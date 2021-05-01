
### GIT Profile of [Justice Ndou](https://justice-ndou.site)

#### Freelance Developer
- Experienced in 
  - Google Cloud Platform Based Projects
  - Python 3.8 / 3.9 
  - Jinja Templates
  - Flask
  - Node.JS
  - Express.JS
  - MySQl, Firebase-Firestore / Datastore / MongoDB / Redis
  - Docker
##
#### My Tech Stack
<img src="https://img.icons8.com/dusk/64/000000/html-5.png"/> <img src="https://img.icons8.com/color/48/000000/css3.png"/> <img src="https://img.icons8.com/wired/48/000000/react.png"/> <img src="https://img.icons8.com/color/48/000000/javascript.png"/> <img src="https://img.icons8.com/color/48/000000/python.png"/> <img src="https://img.icons8.com/color/48/000000/firebase.png"/> <img src="https://img.icons8.com/color/48/000000/mongodb.png"/> <img src="https://img.icons8.com/color/48/000000/mysql.png"/> 
<img src="https://img.icons8.com/color/48/000000/nodejs.png"/>

- #### 🔭 projects I’m currently working on ... 
  - ** [UK Property Development API Proxy](https://github.com/freelancing-solutions/UK-Property-Development-API-Proxy) **
  - ** [Database as a Service (GCP Platform)](https://github.com/freelancing-solutions/pinydesk) **
  - ** [Sellenium & Headless Chrome on Google Cloud Run (Docker Instance)](https://github.com/freelancing-solutions/sellenium-headless-on-GCP-Cloud-Run) **
  - ** [GCP Cloud Run Admin App (Docker, Python3.8, Flask)](https://github.com/freelancing-solutions/Flask-admin_app) **


#### Gists Feed
- [My Programming Gist](https://gist.github.com/freelancing-solutions)


#### Presently Developing [EODHistorical Data for Stock Exchanges ](https://github.com/freelancing-solutions/python-eodhistoricaldata)
```python
  @_handle_environ_error
  @_handle_request_errors
  def get_eod_data(symbol: str, exchange: str, start: typing.Union[str, int] = None, end: typing.Union[str, int] = None,
                   api_key: str = EOD_HISTORICAL_DATA_API_KEY_DEFAULT,
                   session: typing.Union[None, requests.Session] = None) -> typing.Union[pd.DataFrame, None]:
      """
      Returns EOD (end of day data) for a given symbol
      """
      symbol_exchange: str = "{}.{}".format(symbol, exchange)
      session: requests.Session = _init_session(session)
      start, end = _sanitize_dates(start, end)
      endpoint: str = "/eod/{}".format(symbol_exchange)
      url: str = EOD_HISTORICAL_DATA_API_URL + endpoint
      params: dict = {
          "api_token": api_key,
          "from": _format_date(start),
          "to": _format_date(end)
      }
      r: requests.Response = session.get(url, params=params)
      print('status code : {}'.format(r.status_code))

      if r.status_code == requests.codes.ok:
          # NOTE engine='c' which is default does not support skipfooter
          df: typing.Union[pd.DataFrame, None] = pd.read_csv(StringIO(r.text), engine='python',
                                                             skipfooter=1, parse_dates=[0], index_col=0)
          return df
      elif r.status_code == api_key_not_authorized:
          print("API Key Restricted, Try upgrading your API Key: {}".format(__name__))
          return sentinel
      else:
          params["api_token"] = "YOUR_HIDDEN_API"
          raise RemoteDataError(r.status_code, r.reason, _url(url, params))
```

#### Beatiful Python Wrapper Code for Stock Tickers [stock-tickers-data-service](https://github.com/freelancing-solutions/GCP-Based-Database-as-a-Service/blob/main/data_service/views/stocks.py)
```python
    @staticmethod
    def get_stock_data(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            stock_data: dict = kwargs.get('stock_data')
            if 'stock_id' in stock_data and stock_data['stock_id'] != "":
                stock_id: str = stock_data.get('stock_id') or None
            else:
                stock_id = create_id(size=12)
            if 'stock_code' in stock_data and stock_data['stock_code'] != "":
                stock_code: str = stock_data.get('stock_code') or None
            else:
                return jsonify({'status': False, 'message': 'Stock Code is required'}), 500

            if 'stock_name' in stock_data and stock_data['stock_name'] != "":
                stock_name: str = stock_data.get('stock_name') or None
            else:
                return jsonify({'status': False, 'message': 'Stock Name is required'}), 500
            if 'symbol' in stock_data and stock_data['symbol'] != "":
                symbol: str = stock_data.get('symbol') or None
            else:
                return jsonify({'status': False, 'message': 'Stock Symbol is required'}), 500

            return func(stock_id=stock_id, stock_code=stock_code, stock_name=stock_name, symbol=symbol, *args)

        return wrapper
```

- #### Blue IT Marketing Repositories
  - Blue IT Marketing contains more of the projects of which i worked on as a Freelancer
  - [Blue IT Marketing](https://github.com/Blue-IT-Marketing)

- 🔭 started collaborating on the following open source projects ....
  - [dogecoin website](https://github.com/dogecoin/dogecoin.com)
  - [eosjs General purpose library for the EOSIO blockchain.](https://github.com/EOSIO/eosjs)
  - [EOD Historical Data](https://github.com/freelancing-solutions/python-eodhistoricaldata)
  - [GCP Python NDB](https://github.com/freelancing-solutions/python-ndb)
  - [GCP Python Datastore](https://github.com/freelancing-solutions/python-datastore)
--
- 🌱 I’m currently learning ...
  - Python Advanced Concepts : Monads , Lazyness , async,await , asyncio &amp; Coroutines -- completed [2021/01/10]
  - Creating a Blockchain Based Wallet with Python &amp; Node.js
  - Block Chain Explorers with python [bloxplorer](https://pypi.org/project/bloxplorer/)
  - [Ethereum Block Chain Smart Contracts with Solidity](https://ethereum.org/)

- 👯 I’m looking to collaborate on ...
  - **Open Source React.js based projects**
  - **Open Source Javascript based Projects**
  - **Open Source Node.js**
  - **Open Source Python Based Projects**
  - **Open Source Block Chain Based Projects**
--
- 💬 Ask me about ...
  - **Python**
    - ***3.x***
    - ***Jinja2***
    - ***Flask***
    - ***Fast-API***
  - **Javascript**
  - **React.js**
  - **GCP - Google Cloud Platform**
    - ***App-Engine***
      - ***Python 3.x***
    - ***Cloud-Run***
      - ***Python (Flask, Fast-API)***
      - ***Node.js***
    - ***Functions***
      - ***Python (Flask, Fast-API)***
      - ***Node.js***
  - **Docker**
  - **Micro-Services**
  - [Firebase](https://firebase.com)
    - Auth
    - Firestore
    - Functions
  - **Node.js**
  - **Express.js**
  - **Feathers.js**
  - **Code Testing and Error Reporting**
    - Pytest.org 
      - I use Pytest to test my python code, [documentations can be found here](https://docs.pytest.org/en/stable/contents.html)
    - JestJs.io
      - I use Jest for Javascript, Node.js, & React Testing , [Jest Docs Here](https://jestjs.io/docs/en/getting-started.html)
    - Sentry.IO
      - For all (Python, Flask, Node.JS, Javascript, Node.js, React and etc ) my production and development error monitoring and reporting , [Sentry Docs](https://docs.sentry.io/)

- 📫 I am available for ***Freelance*** Gigs
  - Presently available for freelance Gigs, Going Rate
  - **Hourly $ 30.00 / Hour**
  - **$ 450.00 / Gig or Negotiable**
  - HireMe : [UpWork](https://www.upwork.com/o/profiles/users/~01f013b5a637b415f8/)

- 📫 How to reach me: ...
  - **[Contact Me](https://justice-ndou.site/contact)**
  - **Cell : +27762777153**
  - **Email : mobiusndou@gmail.com**
  - **Twitter : [@blueitserver](https://twitter.com/blueitserver)**
  - **Profile : [Justice Ndou](https://justice-ndou.site)**
  - **Upwork Profile : [Justice](https://www.upwork.com/o/profiles/users/~01f013b5a637b415f8/)**

- I welcome contributions
  - Buy me Coffee: [![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/donate?hosted_button_id=7C8NUSPWJX4Z6)
