{% comment %}
This file is licensed under the MIT License (MIT) available on
http://opensource.org/licenses/MIT.
{% endcomment %}
{% assign filename="_includes/ref/bitcoin-core/rpcs/rpcs/setaccount.md" %}

##### SetAccount
{% include helpers/subhead-links.md %}

{% assign summary_setAccount="puts the specified address in the given account." %}

{% autocrossref %}

*Requires wallet support.*

The `setaccount` RPC {{summary_setAccount}}

*Parameter #1---a bitcoin address*

| Name               | Type            | Presence                    | Description
|--------------------|-----------------|-----------------------------|---------------
| Address            | string (base58) | Required<br>(exactly 1)     | The P2PKH or P2SH address to put in the account.  Must already belong to the wallet
{:.ntpd}

*Parameter #2---an account*

| Name               | Type            | Presence                    | Description
|--------------------|-----------------|-----------------------------|---------------
| Account            | string          | Required<br>(exactly 1)     | The name of the account in which the address should be placed.  May be the default account, an empty string ("")
{:.ntpd}

*Result---`null` if successful*

| Name               | Type            | Presence                    | Description
|--------------------|-----------------|-----------------------------|---------------
| `result`           | null            | Required<br>(exactly 1)     | Set to JSON `null` if the address was successfully placed in the account
{:.ntpd}

*Example from Bitcoin Core 0.10.0*

Put the address indicated below in the "doc test" account.

{% highlight bash %}
bitcoin-cli -testnet setaccount \
    mmXgiR6KAhZCyQ8ndr2BCfEq1wNG2UnyG6 "doc test"
{% endhighlight %}

(Success: no result displayed.)

*See also*

* [GetAccount][rpc getaccount]: {{summary_getAccount}}
* [ListAccounts][rpc listaccounts]: {{summary_listAccounts}}
* [GetAddressesByAccount][rpc getaddressesbyaccount]: {{summary_getAddressesByAccount}}

{% endautocrossref %}
