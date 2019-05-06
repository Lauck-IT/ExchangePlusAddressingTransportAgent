ExchangePlusAddressingTransportAgent
==================

forked from eguichar/PlusAgent

> To work correctly you must build the solution with references to 
> the correct Microsoft Exchange DLLs.

An Exchange Transport Protocol agent that implements email address plussing. 

Email Address Plussing allows for any inbox to have disposable emails using a plus.

https://en.wikipedia.org/wiki/Email_address#Sub-addressing


- James DeVincentis
- james@hexhost.net

Usage:
-----
1. Build from source or download pre-compiled DLLS from here: --- old, not working: https://kill-9.me/524/exchange-email-plussing-transport-agent  ---
   new: https://github.com/wech71/ExchangePlusAddressingTransportAgent/releases

2. Copy the compiled .dll file to C:\ExchangeCustomAgents\ExchangePlusAddressingTransportAgent.dll

3. Install the agent and set its priority so it is above the recipient filter.
  ```
  Install-TransportAgent -Name "Email SMTP Plus Addressing Agent" -TransportAgentFactory:ExchangePlusAddressingTransportAgent.Factory -AssemblyPath:"C:\ExchangeCustomAgents\ExchangePlusAddressingTransportAgent.dll"
  Get-TransportAgent
  Set-TransportAgent "Email SMTP Plus Addressing Agent" -Priority:7
  Enable-TransportAgent "Email SMTP Plus Addressing Agent"
  restart-service msexchangetransport
  ```
  
3. Use.
