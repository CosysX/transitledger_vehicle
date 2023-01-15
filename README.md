![TL Logo](https://user-images.githubusercontent.com/18197505/212547039-b71cbd63-66ce-4cc0-985f-c661b9556e3c.png)

# transitledger_vehicle

## How to Use

**This is the Transit Ledger applicaiton which is deployed on a transit vehicle and connects to network to support transit fare collection**

## Usage

### 1. Clone repository

Clone git repository from [cosysx/transitledger_vehicle](https://github.com/cosysx/transitledger_vehicle)
```bash
git clone https://github.com/cosysx/transitledger_vehicle.git
```

### 2. create.env

Create a .env file with your settings in the root directory.

Always start with a new unused seed!

MAX_PAYMENT_TIME is the time until created paymentes aren't checked anymore in minutes (4320 = 3 days to pay, transactions after that are ignored)

If you want to send payouts, without receiving iotas via payments first, send the iotas to the first address of the seed (index 0)

```bash
SEED='REPLACEWITHEIGHTYONETRYTESEED'
IOTANODE='https://nodes.thetangle.org:443'
FALLBACKNODE='https://node01.iotatoken.nl'
MAX_PAYMENT_TIME=4320
PROVIDER_URL='http://localhost:5001/iotapay/api'
NAME="Transit Ledger Vehicle"
VALUE=3
```

### 3. Generate new seed

Create a seed and insert it to your .env file.

#### Linux
 enter this line in your terminal.
```bash
cat /dev/urandom |tr -dc A-Z9|head -c${1:-81}
```

#### Mac
 enter this line in your terminal.
```bash
cat /dev/urandom |LC_ALL=C tr -dc 'A-Z9' | fold -w 81 | head -n 1
```

#### Windows
For Windows, the best way is to use [KeePass](https://keepass.info/), or use one of the two online generators above.

You will want to use the password generator with the following settings:

- Length of generated password: 81
- Check Upper-case (A, B, C, ...)
- Make sure all other boxes are unchecked
- Also include the following characters: 9

### 4. Setup robot

- Insert your provider url from [cosysx/roadledger_facility](https://github.com/cosysx/roadledger_facility)
- Insert your name (example: "Car1")
- Insert an IOTA Value. (example: 3) 

### 5. Build the frontend

enter these lines in your terminal.
```bash
cd frontend
npm install
npm run build
cd ..
```

### 6. Run Vehicle Applciation

enter this lines in your terminal.
```bash
npm install
npm start
```

Copyright (C) 2023 CosysX.
