# Registering and renewing Surfshark VPN WireGurard keys on MikroTik
[SurfsharkWireGuardOnMikroTik](https://github.com/DrunkestCoder/SurfsharkWireGuardOnMikroTik)
***

#### Requirements
* Up-to-date [Surfshark VPN](https://surfshark.club/friend/PdGm94hA) account;
* [Mikrotik JSON Parser](https://github.com/Winand/mikrotik-json-parser);
* Mikrotik RouterOS version 7 or above;
* You mast have a WireGuard private and public keys, you can generate them by creating new WireGuard interface on RouterOS or using [WireGuard Client](https://www.wireguard.com/);
* You can get peer settings from these links: [Generic](https://api.surfshark.com/v4/server/clusters/generic?countryCode=), [Static](https://api.surfshark.com/v4/server/clusters/static?countryCode=), [Multihop](https://api.surfshark.com/v4/server/clusters/double?countryCode=), [Obfuscated](https://api.surfshark.com/v4/server/clusters/obfuscated?countryCode=).
***

#### Usage
1. Set your Surfshark VPN account login and password to SurfsharkLogin and SurfsharkPassword respectively;
2. Set your public keys to variable PublicKeys;
3. If it is first start you should set SurfsharkKeysRegistered to False;
4. Run the script and waiting result in log, If the keys are registered you will see the line "Keys are registered, set SurfsharkKeysRegistered to True";
5. Add the script to the task scheduler to run once a day or less often (the keys are validated for 7 days), example:
        ```
/system/scheduler/add name=SurfsharkRenewWGKeys policy=read,write,policy,test interval=1d start-date=Apr/23/2022 start-time=00:00:00 on-event="/system script run SurfsharkWGKeysRenew"
        ```

[x] By the way, you can add keys for automatic validation that you use on PC/Mobile/Other devices.

** Due to some MikroTik RouterOS limitations, there may be some errors when processing API responses, I tried to minimize their impact as much as possible.
***

## License
[MIT License](https://github.com/git/git-scm.com/blob/main/MIT-LICENSE.txt)

***Hell yeah, is a free software, but provided "AS IS", include all features and bugs!***



###### You can support me by donating some coins so I can buy another bottle of healing liquid to help me get through another day:
+ ###### ETH/USDT/Other Ethereum net tokens/ETC : 0xAAA8603e658F9dEfD5EE44184CF1BF1d1238d318
+ ###### Tron/Other Tron net tokens : TSVsc6AXGLN9C2pyyCh73qxpRmUF8dQLS7
+ ###### TON : EQDfbxqI5Z8ID603316WfVYHeZ6q7nKXiaPphVmIxhwnYUmO
+ ###### XMR : 45JPTmqJKbdfM4no3zebzGjLTc4Cd2XgXXi1KsTqsaFkSsJxW5rzC2yh8DkL3cLjDzSykKzCGHk8qQ3emyJYJwz9KRtKAJb