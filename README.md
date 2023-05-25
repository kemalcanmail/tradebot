# tradebot
Trading is a mode when a bot runs orders according to some strategy.

# Features
* Easy to install and configure
* Initial fill order books
* Dynamic order book building
* Place buy and sell limit or market orders
* Market making with 3 policies: spread, orderbook, optimal
* Spread & liquidity maintenance
* Price range setting
* Arbitrage token price on other trade pairs or exchanges
* Stop-loss and take-profit orders
* Telegram notifications


# Supported exchanges

* [P2PB2B](https://p2pb2b.com)
* [Azbit](https://azbit.com?referralCode=9YVWYAF)
* [StakeCube](https://stakecube.net/?team=adm)
* [Crex24](https://crex24.com/?refid=1q2h0j7dnhbvhr7uh5h0)
* [Binance](https://www.binance.com/en/register?ref=36960933)
* [Bittrex](https://bittrex.com/Account/Register?referralCode=1Z4-3G4-2J0)
* [KuCoin](https://www.kucoin.com/ucenter/signup?rcode=2Mf1KQ)
* [HitBTC](https://hitbtc.com/?ref_id=5a5d39a65d466)
* [BitMart](https://www.bitmart.com/?r=71434)
* [Hotbit](https://www.hotbit.io/register?ref=1147683)
* [BitForex](https://www.bitforex.com/en/register?inviterId=1867433)
* [Bibox](https://www.bibox.com/login/register?id=11387302&lang=en)
* [CoinEx](https://www.coinex.com/register?refer_code=5h2j4)
* [BitZ](https://www.bit-z.com/user/signup?inviter_id=1874503)
* [Bilaxy](https://bilaxy.com/user/register?intro=1428888)
* [Bitrue](https://www.bitrue.com/activity/task/task-landing?inviteCode=EWWLWG&cn=900000)

## Requirements

* Ubuntu 18–22, centOS 8 (we didn't test others)
* NodeJS v16+
* MongoDB v6+ ([installation instructions](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/))

## Setup

```
su - tradebot
git clone https://github.com/kemalcanmail/tradebot
cd ./tradebot
npm i
```

## Pre-launch tuning

The bot will use `config.jsonc`, if available, or `config.default.jsonc` otherwise.

```
cp config.default.jsonc config.jsonc
nano config.jsonc
```

Parameters: see comments in config file.

## Launching

You can start the Bot with the `node app` command, but it is recommended to use the process manager for this purpose.

```
pm2 start app.js --name tradebot
```

## Add a Bot to cron

```
crontab -e
```

Add string:

```
@reboot cd /home/tradebot && pm2 start app.js --name tradebot
```

## Updating

```
su - tradebot
cd ./tradebot
pm2 stop tradebot
git pull
npm i
```

Update `config.jsonc` if `config.default.jsonc` changed.

Then `pm2 restart tradebot`.

## Troubleshooting

If you have any issues with the bot, please, create an issue on GitHub. We will try to help you.
