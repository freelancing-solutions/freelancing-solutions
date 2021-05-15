
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


#### Mocking ndb.Model.put , query and fetch to test ndb.Model [query-mock](https://gist.github.com/freelancing-solutions/fdd288192682d19b96bfaac6426523bb)
```python
class BrokerQueryMock:
    broker_instance: Broker = Broker()
    results_range: int = randint(0, 100)

    def __init__(self):
        pass

    def fetch(self) -> typing.List[Broker]:
        return [self.broker_instance for _ in range(self.results_range)]

    def get(self) -> Broker:
        return self.broker_instance


broker_data_mock: dict = {
    "broker_id": create_id(),
    "broker_code": "ASD",
    "broker_name": "ASD"
}


# noinspection PyShadowingNames
def test_create_broker(mocker):
    mocker.patch('google.cloud.ndb.Model.put', return_value=create_id())
    mocker.patch('google.cloud.ndb.Model.query', return_value=BrokerQueryMock())

    with test_app().app_context():
        stock_view_instance: StockView = StockView()
        mocker.patch('data_service.views.stocks.StockView.broker_id_exist', return_value=False)
        mocker.patch('data_service.views.stocks.StockView.broker_code_exist', return_value=False)
        response, status = stock_view_instance.create_broker_data(broker_data=broker_data_mock)
        assert status == 200, "Unable to create broker data"

        mocker.patch('data_service.views.stocks.StockView.broker_code_exist', return_value=True)
        response, status = stock_view_instance.create_broker_data(broker_data=broker_data_mock)
        assert status == 500, "Creating duplicate brokers"

        mocker.patch('data_service.views.stocks.StockView.broker_code_exist', return_value=False)
        mocker.patch('data_service.views.stocks.StockView.broker_id_exist', return_value=True)
        response, status = stock_view_instance.create_broker_data(broker_data=broker_data_mock)
        assert status == 500, "Creating duplicate brokers"

    mocker.stopall()
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
  - Buy me Coffee: [!Dogecoin :] DKrBuA8A7N3RRfH4qKn6tnkBe9oLCWzquN 


![Visitor Count](https://profile-counter.glitch.me/freelancing-solutions/count.svg)
