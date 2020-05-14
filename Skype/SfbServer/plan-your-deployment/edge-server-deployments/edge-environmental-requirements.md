---
title: Requisiti ambientali dei server perimetrali in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Riepilogo: informazioni sui requisiti ambientali per Edge Server in Skype for Business Server.'
ms.openlocfilehash: 8e2ec6d2afc53648fe50af4cd5ab02ad21d11643
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219926"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Requisiti ambientali dei server perimetrali in Skype for Business Server
 
**Riepilogo:** Informazioni sui requisiti ambientali per Edge Server in Skype for Business Server.
  
La pianificazione e la preparazione devono avere luogo all'esterno dell'ambiente server Edge di Skype for Business Server. In questo articolo verranno riportate le operazioni preliminari che devono essere eseguite nell'ambiente organizzativo, come indicato nell'elenco seguente:
  
- [Pianificazione della topologia](edge-environmental-requirements.md#TopoPlan)
    
- [Pianificazione DNS](edge-environmental-requirements.md#DNSPlan)
    
- [Pianificazione del certificato](edge-environmental-requirements.md#CertPlan)
    
- [Pianificazione di porte e firewall](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Pianificazione della topologia
<a name="TopoPlan"> </a>

Le topologie del server perimetrale di Skype for Business Server sono in grado di utilizzare:
  
- Indirizzi IP pubblici instradabili.
    
- Indirizzi IP privati non instradabili, se viene utilizzato NAT ( **Symmetric** Network Address Translation).
    
> [!TIP]
> È possibile configurare il server perimetrale per l'utilizzo di un singolo indirizzo IP con porte distinte per ogni servizio oppure utilizzare indirizzi IP distinti per ogni servizio, ma utilizzare la stessa porta predefinita (che per impostazione predefinita sarà TCP 443). Per ulteriori informazioni, fare quanto segue nella sezione requisiti IP address. 
  
Se si scelgono indirizzi IP privati non instradabili con NAT, tenere presenti i seguenti punti:
  
- È necessario utilizzare indirizzi IP privati instradabili su **tutte e tre le** interfacce esterne.
    
- È necessario configurare NAT **simmetrico** per il traffico in ingresso e in uscita. Symmetric NAT è l'unico NAT supportato che è possibile utilizzare con Skype for Business Server Edge Server.
    
- Configurare il NAT in modo che non modifichi gli indirizzi di origine in ingresso. Per trovare il percorso multimediale ottimale, è necessario che il servizio A/V Edge sia in grado di ricevere l'indirizzo di origine in ingresso.
    
- I server perimetrali devono essere in grado di comunicare tra loro dagli indirizzi IP pubblici A/V Edge. Il firewall deve consentire questo traffico.
    
- NAT può essere utilizzato **solo** per i server perimetrali consolidati in scala, se si utilizza il bilanciamento del carico DNS. Se si usa il bilanciamento del carico hardware (HLB), è necessario utilizzare indirizzi IP instradabili pubblicamente **senza** NAT.
    
Non vi sono problemi con le interfacce di accesso, Web Conferencing e A/V Edge dietro un router o un firewall che esegue NAT simmetrica sia per le topologie di server perimetrali consolidate singole che in scala (purché non si utilizzi il bilanciamento del carico hardware).
  
### <a name="summary-of-edge-server-topology-options"></a>Riepilogo delle opzioni di topologia del server perimetrale

Sono disponibili diverse opzioni di topologia per le distribuzioni di Skype for Business Server Edge Server:
  
- Singolo server perimetrale consolidato con indirizzi IP privati e NAT
    
- Server perimetrale consolidato singolo con indirizzi IP pubblici
    
- Server perimetrale consolidato in scala con indirizzi IP privati e NAT
    
- Server perimetrale consolidato in scala con indirizzi IP pubblici
    
- Server perimetrale consolidato in scala con dispositivi di bilanciamento del carico hardware
    
Per agevolare la scelta, è presente la seguente tabella che fornisce un riepilogo delle opzioni disponibili per ogni topologia:
  
|**Topologia**|**Disponibilità elevata**|**Record DNS aggiuntivi necessari per il server perimetrale esterno nel pool perimetrale?**|**Failover Edge per le sessioni di Skype for Business Server**|**Failover Edge per le sessioni di Federazione di Skype for Business Server**|
|:-----|:-----|:-----|:-----|:-----|
|Singolo server perimetrale consolidato con indirizzi IP privati e NAT  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Server perimetrale consolidato singolo con indirizzi IP pubblici  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Server perimetrale consolidato in scala con indirizzi IP privati e NAT (bilanciamento del carico DNS)  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì&sup1;  <br/> |
|Server perimetrale consolidato in scala con indirizzi IP pubblici (bilanciamento del carico DNS)  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì&sup1;  <br/> |
|Server perimetrale consolidato in scala con dispositivi di bilanciamento del carico hardware  <br/> |Sì  <br/> |No (un record A DNS per IP virtuale)  <br/> |Sì  <br/> |Sì  <br/> |
   
&sup1; Il failover degli utenti remoti di messaggistica unificata di Exchange con il bilanciamento del carico DNS richiede Exchange 2013 o versione successiva.
  
### <a name="ip-address-requirements"></a>Requisiti per l'indirizzo IP

A livello fondamentale, tre servizi richiedono gli indirizzi IP. Servizio Access Edge, servizio Web Conferencing Edge e servizio A/V Edge. È possibile utilizzare tre indirizzi IP, uno per ognuno dei servizi oppure utilizzarne uno e scegliere di inserire ogni servizio su una porta diversa (è possibile estrarre la sezione [pianificazione porte e firewall](edge-environmental-requirements.md#PortFirewallPlan) per ulteriori informazioni su parte di esso). Per un singolo ambiente perimetrale consolidato, questo è più o meno.
  
> [!NOTE]
> Come indicato in alto, è possibile scegliere di disporre di un indirizzo IP per tutti e tre i servizi ed eseguirli in porte diverse. Tuttavia, per essere chiari, non è consigliabile. Se i clienti non sono in grado di accedere alle porte alternative che si utilizzeranno in questo scenario, non possono accedere alle funzionalità complete dell'ambiente Edge. 
  
Può essere un po' più complicato con topologie consolidate in scala, quindi è possibile esaminare alcune tabelle che definiscono i requisiti di indirizzo IP, tenendo presente che i punti decisionali principali per la selezione della topologia sono disponibilità elevata e bilanciamento del carico. La disponibilità elevata può influire sulla scelta del bilanciamento del carico (ne parleremo di più dopo le tabelle).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisiti per l'indirizzo IP per il perimetro consolidato in scala (indirizzo IP per ruolo)

|**Numero di server perimetrali per pool**|**Numero di indirizzi IP necessari per il bilanciamento del carico DNS**|**Numero di indirizzi IP necessari per il bilanciamento del carico hardware**|
|:-----|:-----|:-----|
|2   <br/> |6   <br/> |3 (1 per VIP) + 6  <br/> |
|3   <br/> |9   <br/> |3 (1 per VIP) + 9  <br/> |
|4   <br/> |12   <br/> |3 (1 per VIP) + 12  <br/> |
|5   <br/> |15   <br/> |3 (1 per VIP) + 15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Requisiti per l'indirizzo IP per il perimetro consolidato in scala (indirizzo IP singolo per tutti i ruoli)

|**Numero di server perimetrali per pool**|**Numero di indirizzi IP necessari per il bilanciamento del carico DNS**|**Numero di indirizzi IP necessari per il bilanciamento del carico hardware**|
|:-----|:-----|:-----|
|2   <br/> |2   <br/> |1 (1 per IP virtuale) + 2  <br/> |
|3   <br/> |3   <br/> |3 (1 per IP virtuale) + 6  <br/> |
|4   <br/> |4   <br/> |4 (1 per IP virtuale) + 6  <br/> |
|5   <br/> |5   <br/> |5 (1 per IP virtuale) + 6  <br/> |
   
Per ulteriori informazioni, vedere pianificazione.
  
- **Disponibilità elevata**: se è necessaria un'elevata disponibilità nella distribuzione, è necessario distribuire almeno due server perimetrali in un pool. È opportuno sottolineare che un singolo pool di server perimetrali supporta fino a un massimo di 12 (anche se il generatore di topologie consentirà di aggiungere fino a 20, non testato o supportato, pertanto si consiglia di non eseguire questa operazione). Se sono necessari più di 12 server perimetrali, è necessario creare pool di Edge aggiuntivi.
    
- **Bilanciamento del carico hardware**: si consiglia il bilanciamento del carico DNS per la maggior parte degli scenari. Il bilanciamento del carico hardware è supportato, ovviamente, ma in particolare è necessario per un singolo scenario rispetto al bilanciamento del carico DNS:
    
  - Accesso esterno alla messaggistica unificata di Exchange 2007 o Exchange 2010 (senza SP).
    
- **Bilanciamento del carico DNS**: per la messaggistica unificata, Exchange 2010 SP1 e versioni successive sono in grado di supportare il bilanciamento del carico DNS. Si noti che, se è necessario andare con il bilanciamento del carico DNS per una versione precedente di Exchange, funzionerà, ma tutto il traffico per questo passerà al primo server del pool e, se non è disponibile, il traffico avrà esito negativo.
    
    Il bilanciamento del carico DNS è consigliato anche se si sta eseguendo la Federazione con società che utilizzano:
- Skype for Business Server 2015:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft 365 o Office 365
- Skype for Business Server 2019:
    - Lync Server 2013
    - Skype for Business Server 2015
    - Microsoft 365 o Office 365
    
## <a name="dns-planning"></a>Pianificazione DNS
<a name="DNSPlan"> </a>

Quando si tratta di una distribuzione di Skype for Business Server Edge Server, è fondamentale prepararsi per il DNS in modo appropriato. Con i record giusti sul posto, la distribuzione sarà molto più semplice. Si spera di aver scelto una topologia nella sezione precedente, come si intende fare una panoramica e quindi elencare un paio di tabelle che delineano i record DNS per tali scenari. Per la lettura più approfondita, se necessario, avremo anche una [pianificazione DNS avanzata del server perimetrale per Skype for Business Server](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) .
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>Record DNS per scenari con server perimetrali consolidati singoli

Si tratta dei record DNS di cui si avrà bisogno per un server perimetrale singe usando IP pubblici o IP privati con NAT. Poiché si tratta di dati di esempio, vengono illustrati gli indirizzi IP di esempio, in modo da poter elaborare le proprie voci più facilmente:
  
- Scheda di rete interna: 172.25.33.10 (non è assegnato alcun gateway predefinito)
    
    > [!NOTE]
    > Verificare che esista una route dalla rete che contiene l'interfaccia interna del server perimetrale alle reti che contengono server che eseguono i client Skype for business o Lync Server 2013 (ad esempio, da 172.25.33.0 a 192.168.10.0). 
  
- Scheda di rete esterna:
    
  - Indirizzi IP pubblici:
    
  - Access Edge: 131.107.155.10 (questo è il principale, con il gateway predefinito impostato sul router pubblico, es: 131.107.155.1)
    
  - Web Conferencing Edge: 131.107.155.20 (secondario)
    
  - A/V Edge: 131.107.155.30 (secondario)
    
  Le conferenze Web e gli indirizzi IP pubblici A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà del protocollo Internet versione 4 (TCP/IPv4) e del protocollo Internet versione 6 (TCP/IPv6) delle proprietà della connessione all'area locale in Windows Server.
    
  - Indirizzi IP privati:
    
  - Access Edge: 10.45.16.10 (questo è il principale, con il gateway predefinito impostato sul router, es: 10.45.16.1)
    
  - Web Conferencing Edge: 10.45.16.20 (secondario)
    
  - A/V Edge: e 10.45.16.30 (secondario)
    
Le conferenze Web e gli indirizzi IP pubblici A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà del protocollo Internet versione 4 (TCP/IPv4) e del protocollo Internet versione 6 (TCP/IPv6) delle proprietà della connessione all'area locale in Windows Server.
  
> [!TIP]
>Sono disponibili altre configurazioni possibili:
  
- È possibile utilizzare un indirizzo IP nella scheda di rete esterna. Non è consigliabile perché sarà necessario distinguere tra i servizi di thee utilizzando porte diverse (operazione che è possibile eseguire in Skype for Business Server) ma esistono alcuni firewall che potrebbero bloccare le porte alternative. Per ulteriori informazioni, vedere la sezione relativa alla [pianificazione di porte e firewall](edge-environmental-requirements.md#PortFirewallPlan) .
    
- È possibile disporre di tre schede di rete esterne anziché una e assegnare uno degli IP dei servizi a ognuno di essi. Perché eseguire questa operazione? I servizi potrebbero essere separati e se qualcosa dovesse andare storto, ciò renderebbe più facile la risoluzione dei problemi e potrebbe consentire agli altri servizi di continuare a funzionare durante la risoluzione di un problema.
    
|**Posizione**|**Tipo**|**Porta**|**FQDN o record DNS**|**Indirizzo IP o FQDN**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS esterno  <br/> |Un record  <br/> |ND  <br/> |sip.contoso.com  <br/> |**pubblico:** 131.107.155.10 <br/> **privato:** 10.45.16.10 <br/> |Interfaccia esterna per il servizio Access Edge. Sarà necessario uno per ogni dominio SIP con gli utenti di Skype for business.  <br/> |
|DNS esterno  <br/> |Un record  <br/> |ND  <br/> |webcon.contoso.com  <br/> |**pubblico:** 131.107.155.20 <br/> **privato:** 10.45.16.20 <br/> |Interfaccia esterna per il servizio Web Conferencing Edge.  <br/> |
|DNS esterno  <br/> |Un record  <br/> |ND  <br/> |av.contoso.com  <br/> |**pubblico:** 131.107.155.30 <br/> **privato:** e 10.45.16.30 <br/> |Interfaccia esterna per il servizio A/V Edge.  <br/> |
|DNS esterno  <br/> |record SRV  <br/> |443  <br/> |_sip. _tls. contoso. com  <br/> |sip.contoso.com  <br/> |Interfaccia esterna per il servizio Access Edge. Questo record SRV è necessario per i client Skype for Business Server, Lync Server 2013 e Lync Server 2010 per funzionare esternamente. Sarà necessario uno per ogni dominio con gli utenti di Skype for business.  <br/> |
|DNS esterno  <br/> |record SRV  <br/> |5061  <br/> |_sipfederationtls. _tcp. contoso. com  <br/> |sip.contoso.com  <br/> |Interfaccia esterna per il servizio Access Edge. Questo record SRV è necessario per l'individuazione automatica del DNS dei partner federati denominati domini SIP consentiti. Sarà necessario uno per ogni dominio con gli utenti di Skype for business.  <br/> |
|DNS interno  <br/> |Un record  <br/> |ND  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |Interfaccia interna per il server perimetrale consolidato.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>Record DNS per scenari di server perimetrali e DNS con scalabilità orizzontale

Si tratta dei record DNS di cui si avrà bisogno per un server perimetrale singe usando IP pubblici o IP privati con NAT. Poiché si tratta di dati di esempio, vengono illustrati gli indirizzi IP di esempio, in modo da poter elaborare le proprie voci più facilmente:
  
- Scheda di rete interna:
    
  - Nodo 1:172.25.33.10 (non è assegnato alcun gateway predefinito)
    
  - Nodo 2:172.25.33.11 (non è assegnato alcun gateway predefinito)
    
    > [!NOTE]
    > Verificare che esista una route dalla rete che contiene l'interfaccia interna del server perimetrale alle reti che contengono server che eseguono i client Skype for business o Lync Server 2013 (ad esempio, da 172.25.33.0 a 192.168.10.0). 
  
- Scheda di rete esterna:
    
  - Nodo 1
    
     - Indirizzi IP pubblici:
    
        - Access Edge: 131.107.155.10 (questo è il principale, con il gateway predefinito impostato sul router pubblico, es: 131.107.155.1)
    
        - Web Conferencing Edge: 131.107.155.20 (secondario)
    
        - A/V Edge: 131.107.155.30 (secondario)
    
          Le conferenze Web e gli indirizzi IP pubblici A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà del protocollo Internet versione 4 (TCP/IPv4) e del protocollo Internet versione 6 (TCP/IPv6) delle proprietà della connessione all'area locale in Windows Server.
    
    - Indirizzi IP privati:
    
         - Access Edge: 10.45.16.10 (questo è il principale, con il gateway predefinito impostato sul router, es: 10.45.16.1)
    
         - Web Conferencing Edge: 10.45.16.20 (secondario)
    
         - A/V Edge: e 10.45.16.30 (secondario)
    
      Le conferenze Web e gli indirizzi IP pubblici A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà del protocollo Internet versione 4 (TCP/IPv4) e del protocollo Internet versione 6 (TCP/IPv6) delle proprietà della connessione all'area locale in Windows Server.
    
  - Nodo 2
    
    - Indirizzi IP pubblici:
    
      - Access Edge: 131.107.155.11 (questo è il principale, con il gateway predefinito impostato sul router pubblico, es: 131.107.155.1)
    
      - Web Conferencing Edge: 131.107.155.21 (secondario)
    
      - A/V Edge: 131.107.155.31 (secondario)
    
      Le conferenze Web e gli indirizzi IP pubblici A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà del protocollo Internet versione 4 (TCP/IPv4) e del protocollo Internet versione 6 (TCP/IPv6) delle proprietà della connessione all'area locale in Windows Server.
    
  - Indirizzi IP privati:
    
    - Access Edge: 10.45.16.11 (questo è il principale, con il gateway predefinito impostato sul router, es: 10.45.16.1)
    
    - Web Conferencing Edge: 10.45.16.21 (secondario)
    
    - A/V Edge: 10.45.16.31 (secondario)
    
      Le conferenze Web e gli indirizzi IP pubblici A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà del protocollo Internet versione 4 (TCP/IPv4) e del protocollo Internet versione 6 (TCP/IPv6) delle proprietà della connessione all'area locale in Windows Server.
    
Sono disponibili altre configurazioni possibili:
  
- È possibile utilizzare un indirizzo IP nella scheda di rete esterna. Non è consigliabile perché sarà necessario distinguere tra i servizi di thee utilizzando porte diverse (operazione che è possibile eseguire in Skype for Business Server) ma esistono alcuni firewall che potrebbero bloccare le porte alternative. Per ulteriori informazioni, vedere la sezione relativa alla [pianificazione di porte e firewall](edge-environmental-requirements.md#PortFirewallPlan) .
    
- È possibile disporre di tre schede di rete esterne anziché una e assegnare uno degli IP dei servizi a ognuno di essi. Perché eseguire questa operazione? I servizi potrebbero essere separati e se qualcosa dovesse andare storto, ciò renderebbe più facile la risoluzione dei problemi e potrebbe consentire agli altri servizi di continuare a funzionare durante la risoluzione di un problema.
    
|**Posizione**|**Tipo**|**Porta**|**FQDN o record DNS**|**Indirizzo IP o FQDN**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS esterno  <br/> |Un record  <br/> |ND  <br/> |sip.contoso.com  <br/> |**public:** 131.107.155.10 e 131.107.155.11 <br/> **privato:** 10.45.16.10 e 10.45.16.11 <br/> |Interfaccia esterna per il servizio Access Edge. Sarà necessario uno per ogni dominio SIP con gli utenti di Skype for business.  <br/> |
|DNS esterno  <br/> |Un record  <br/> |ND  <br/> |webcon.contoso.com  <br/> |**public:** 131.107.155.20 e 131.107.155.21 <br/> **privato:** 10.45.16.20 e 10.45.16.21 <br/> |Interfaccia esterna per il servizio Web Conferencing Edge.  <br/> |
|DNS esterno  <br/> |Un record  <br/> |ND  <br/> |av.contoso.com  <br/> |**public:** 131.107.155.30 e 131.107.155.31 <br/> **privato:** e 10.45.16.30 e 10.45.16.31 <br/> |Interfaccia esterna per il servizio A/V Edge.  <br/> |
|DNS esterno  <br/> |record SRV  <br/> |443  <br/> |_sip. _tls. contoso. com  <br/> |sip.contoso.com  <br/> |Interfaccia esterna per il servizio Access Edge. Questo record SRV è necessario per i client Skype for Business Server, Lync Server 2013 e Lync Server 2010 per funzionare esternamente. Sarà necessario uno per ogni dominio con Skype for business.  <br/> |
|DNS esterno  <br/> |record SRV  <br/> |5061  <br/> |_sipfederationtls. _tcp. contoso. com  <br/> |sip.contoso.com  <br/> |Interfaccia esterna per il servizio Access Edge. Questo record SRV è necessario per l'individuazione automatica del DNS dei partner federati denominati domini SIP consentiti. Sarà necessario uno per ogni dominio con Skype for business.  <br/> |
|DNS interno  <br/> |Un record  <br/> |ND  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 e 172.25.33.11  <br/> |Interfaccia interna per il server perimetrale consolidato.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Record DNS per la Federazione (tutti gli scenari)

|**Posizione**|**Tipo**|**Porta**|**FQDN**|**Record host FQDN**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS esterno  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp. contoso. com  <br/> |sip.contoso.com  <br/> |L'interfaccia esterna SIP Access Edge necessaria per l'individuazione automatica dei DNS. Utilizzato dagli altri partner di Federazione potenziali. È conosciuto anche come "Consenti domini SIP". Sarà necessario uno di questi per ogni dominio SIP con gli utenti di Skype for business.  <br/><br/> **Nota:** Questo record SRV è necessario per la mobilità e la casa di compensazione delle notifiche push. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Record DNS per il protocollo di messaggistica e presenza estensibile

|**Posizione**|**Tipo**|**Porta**|**FQDN**|**Indirizzo IP o record host FQDN**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS esterno  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server. _tcp. contoso. com  <br/> |xmpp.contoso.com  <br/> |Interfaccia proxy XMPP nel servizio Access Edge o nel pool di server perimetrali. È necessario ripetere questa operazione in base alle esigenze per tutti i domini SIP interni con gli utenti abilitati per Skype for Business Server, in cui è consentito il contatto con i contatti XMPP tramite:  <br/> • un criterio globale  <br/> • un criterio sito in cui l'utente è abilitato  <br/> • un criterio utente applicato all'utente abilitato di Skype for Business Server  <br/> È inoltre necessario configurare un criterio XMPP consentito nel criterio degli utenti federati XMPP.  <br/> |
|DNS esterno  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |Indirizzo IP del servizio Access Edge nel server perimetrale o nel pool perimetrale che ospita il servizio proxy XMPP  <br/> |Questo indica il servizio Access Edge nel server perimetrale o nel pool di Edge che ospita il servizio proxy XMPP. In genere, il record SRV creato punterà a questo record host (A o AAAA).  <br/> |
   
> [!NOTE]
> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015 ma non sono più supportati in Skype for Business Server 2019. Per ulteriori informazioni, vedere [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .

## <a name="certificate-planning"></a>Pianificazione dei certificati
<a name="CertPlan"> </a>

Skype for Business Server utilizza i certificati per comunicazioni sicure e crittografate tra server e da server a client. Come previsto, i certificati dovranno disporre di record DNS per i server che corrispondono a qualsiasi nome soggetto (SN) e nome alternativo soggetto (SAN) sui certificati. In questo modo, nella fase di pianificazione, è possibile verificare che gli FQDN giusti siano registrati in DNS per le voci SN e SAN per i certificati.
  
Verranno discusse separatamente le esigenze dei certificati esterni e interni e quindi verrà esaminata una tabella che fornisce i requisiti per entrambi.
  
### <a name="external-certificates"></a>Certificati esterni

Almeno, il certificato assegnato alle interfacce del server perimetrale esterno dovrà essere fornito da un'autorità di certificazione (CA) pubblica. Non è possibile consigliarvi un'autorità di certificazione specifica, ma è presente un elenco di CAs, partner di certificati per le [comunicazioni unificate](/SkypeForBusiness/certification/services-ssl) che può essere utilizzato per controllare se l'autorità di certificazione preferita è elencata.
  
Quando sarà necessario inviare una richiesta a un'autorità di certificazione per il certificato pubblico e come procedere? Per ottenere questo risultato, è possibile eseguire una coppia di modi:
  
- È possibile passare all'installazione di Skype for Business Server e quindi alla distribuzione di server perimetrali. La distribuzione guidata di Skype for Business Server avrà un passaggio per generare una richiesta di certificato, che sarà quindi possibile inviare all'autorità di certificazione selezionata.
    
- È inoltre possibile utilizzare i comandi di Windows PowerShell per generare la richiesta, se questo è più in linea con le esigenze aziendali o la strategia di distribuzione.
    
- Infine, è possibile che l'autorità di certificazione disponga di un proprio processo di invio, che può coinvolgere anche Windows PowerShell o un altro metodo. In tal caso, è necessario fare affidamento sulla documentazione, oltre alle informazioni fornite qui per il riferimento.
    
Dopo aver ottenuto il certificato, è necessario andare avanti e assegnarlo a questi servizi in Skype for Business Server:
  
- Interfaccia del servizio Access Edge
    
- Interfaccia del servizio Web Conferencing Edge
    
- Servizio di autenticazione audio/video (non confondere questo problema con il servizio A/V Edge, in quanto non utilizza un certificato per crittografare i flussi audio e video)
    
> [!IMPORTANT]
> Tutti i server perimetrali (se appartengono allo stesso pool di server perimetrali) devono avere lo stesso certificato con la stessa chiave privata per il servizio di autenticazione Media Relay. 
  
### <a name="internal-certificates"></a>Certificati interni

Per l'interfaccia del server perimetrale interno, è possibile utilizzare un certificato pubblico di un'autorità di certificazione pubblica oppure un certificato emesso dall'autorità di certificazione interna dell'organizzazione. La cosa da ricordare sul certificato interno è che utilizza una voce SN e non le voci di SAN, quindi non è necessario preoccuparsi di SAN sul cert interno.
  
### <a name="required-certificates-table"></a>Tabella certificati necessari

È presente un tabella che fornisce assistenza per le richieste. Le voci FQDN sono solo per i domini di esempio. È necessario effettuare le richieste in base ai propri domini pubblici e privati, ma ecco una guida a ciò che è stato usato:
  
- Contoso <span></span> . com: FQDN pubblico
    
- Fabrikam <span></span> . com: Second FQDN pubblico (aggiunta come dimostrazione di cosa richiedere se si dispone di più domini SIP)
    
- Contoso <span></span> .NET: Internal Domain
    
#### <a name="edge-certificate-table"></a>Tabella certificate Edge

Indipendentemente dal fatto che si stia eseguendo un singolo server perimetrale o un pool di Edge, questo è ciò che è necessario per il certificato:
  
|**Componente**|**Nome soggetto (SN)**|**Nomi alternativi del soggetto (SAN) ordine/nome**|**Note**|
|:-----|:-----|:-----|:-----|
|Perimetro esterno  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Questo è il certificato che è necessario richiedere da un'autorità di certificazione pubblica. Dovrà essere assegnato alle interfacce perimetrali esterne per le seguenti operazioni:  <br/> • Access Edge  <br/> • Web Conferencing Edge  <br/> • Autenticazione audio/video  <br/> <br/>La buona notizia è che i SANs vengono aggiunti automaticamente alla richiesta di certificato e quindi il certificato dopo l'invio della richiesta, in base a quanto definito per la distribuzione in Generatore di topologie. È necessario aggiungere solo le voci di SAN per eventuali altri domini SIP o altre voci che è necessario supportare. Perché sip.contoso.com è replicato in questa istanza? Che si verifica automaticamente anche ed è necessario che le operazioni funzionino correttamente.  <br/><br/> **Nota:** Questo certificato può essere utilizzato anche per la connettività di messaggistica istantanea pubblica. Non è necessario eseguire alcuna operazione in modo diverso, ma nelle versioni precedenti di questa documentazione è stato elencato come tabella separata e ora non lo è. <br/> |
|Perimetro interno  <br/> |sfbedge.contoso.com  <br/> |ND  <br/> |È possibile ottenere questo certificato da un'autorità di certificazione pubblica o da un'autorità di certificazione interna. Sarà necessario contenere il server EKU (Enhanced Key Usage) e assegnarlo all'interfaccia perimetrale interna.  <br/> |
   
Se è necessario un certificato per il protocollo XMPP (Extensible Messaging and Presence Protocol), avrà un aspetto identico alle voci di tabella perimetrale esterne precedenti, ma avrà le due voci di SAN aggiuntive seguenti:
  
- XMPP. <span></span> Contoso <span></span> . com
    
- \*. contoso <span></span> . com
    
Tieni presente che attualmente XMPP è supportato solo in Skype for Business Server per Google Talk, se vuoi o hai bisogno di usarlo per qualcos'altro, devi confermare la funzionalità con il fornitore di terze parti coinvolto.
  
## <a name="port-and-firewall-planning"></a>Pianificazione di porte e firewall
<a name="PortFirewallPlan"> </a>

Ottenere il diritto di pianificazione per le porte e i firewall per le distribuzioni di Skype for Business Server Edge Server può salvare giorni o settimane di risoluzione dei problemi e stress. Di conseguenza, verrà elencata una coppia di tabelle che indicheranno l'utilizzo del protocollo e le porte che è necessario aprire, in ingresso e in uscita, sia per gli scenari NAT che per quelli di IP pubblico. Sono inoltre disponibili tabelle separate per gli scenari di bilanciamento del carico hardware e altre informazioni. Per ulteriori informazioni, esistono anche alcuni [scenari server perimetrali in Skype for Business Server](scenarios.md) che è possibile estrarre per i problemi di distribuzione specifici.
  
### <a name="general-protocol-usage"></a>Utilizzo del protocollo generale

Prima di esaminare le tabelle di riepilogo per i firewall esterni e interni, è consigliabile considerare anche la tabella seguente:
  
|**Trasporto audio/video**|**Usage**|
|:-----|:-----|
|UDP  <br/> |Il protocollo di livello di trasporto preferito per audio e video.  <br/> |
|TCP  <br/> |Protocollo di livello di trasporto di fallback per audio e video.  <br/> Il protocollo di trasporto Layer obbligatorio per la condivisione di applicazioni su Skype for Business Server, Lync Server 2013 e Lync Server 2010.  <br/> Il protocollo di trasporto Layer necessario per il trasferimento di file in Skype for Business Server, Lync Server 2013 e Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tabella di riepilogo del firewall per le porte esterne

L'indirizzo IP di origine e l'indirizzo IP di destinazione conterranno informazioni per gli utenti che utilizzano indirizzi IP privati con NAT, nonché persone che utilizzano indirizzi IP pubblici. Questo coprirà tutte le permutazioni negli [scenari del server perimetrale nella sezione Skype for Business Server](scenarios.md) .
  
|**Ruolo o protocollo**|**TCP o UDP**|**Porta di destinazione o intervallo di porte**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Non supportato in Skype for Business Server 2019 |TCP  <br/> |5269  <br/> |Qualsiasi  <br/> |Servizio proxy XMPP (condivide un indirizzo IP con il servizio Access Edge  <br/> |Il servizio proxy XMPP accetta il traffico proveniente dai contatti XMPP nelle federazioni XMPP definite.  <br/> |
|Accesso/HTTP  <br/> |TCP  <br/> |80  <br/> |**IP privato tramite NAT:** Servizio Access Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Access Edge Server perimetrale <br/> |Qualsiasi  <br/> |Revoca del certificato e controllo e recupero CRL.  <br/> |
|Accesso/DNS  <br/> |TCP  <br/> |53  <br/> |**IP privato tramite NAT:** Servizio Access Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Access Edge Server perimetrale <br/> |Qualsiasi  <br/> |Query DNS su TCP.  <br/> |
|Accesso/DNS  <br/> |UDP  <br/> |53  <br/> |**IP privato tramite NAT:** Servizio Access Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Access Edge Server perimetrale <br/> |Qualsiasi  <br/> |Query DNS su UDP.  <br/> |
|Accesso/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio Access Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Access Edge Server perimetrale <br/> |Traffico SIP da client a server per l'accesso degli utenti esterni.  <br/> |
|Accesso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio Access Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Access Edge Server perimetrale <br/> |Per la connettività di messaggistica istantanea pubblica e federata con SIP.  <br/> |
|Accesso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privato tramite NAT:** Servizio Access Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Access Edge Server perimetrale <br/> |Qualsiasi  <br/> |Per la connettività di messaggistica istantanea pubblica e federata con SIP.  <br/> |
|Web Conferencing/PSOM (TLS)  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio Web Conferencing Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Web Conferencing Edge Server perimetrale <br/> |Supporto per Web Conferencing.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**IP privato tramite NAT:** Servizio A/V Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio A/V Edge Server perimetrale <br/> |Qualsiasi  <br/> |Viene utilizzato per l'inoltro del traffico multimediale.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**IP privato tramite NAT:** Servizio A/V Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio A/V Edge Server perimetrale <br/> |Qualsiasi  <br/> |Viene utilizzato per l'inoltro del traffico multimediale.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**IP privato tramite NAT:** Servizio A/V Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio A/V Edge Server perimetrale <br/> |Qualsiasi  <br/> |3478 in uscita è:  <br/> • Utilizzato da Skype for Business Server per determinare la versione del server perimetrale che comunica con.  <br/> • Utilizzato per il traffico multimediale tra server perimetrali.  <br/> • Obbligatorio per la Federazione con Lync Server 2010.  <br/> • Necessario se sono distribuiti più pool di server perimetrali all'interno dell'organizzazione.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio A/V Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio A/V Edge Server perimetrale <br/> |Negoziazione STUN/turno dei candidati su UDP sulla porta 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio A/V Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio A/V Edge Server perimetrale <br/> |Negoziazione STUN/turno dei candidati su TCP sulla porta 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**IP privato tramite NAT:** Servizio A/V Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio A/V Edge Server perimetrale <br/> |Qualsiasi  <br/> |Negoziazione STUN/turno dei candidati su TCP sulla porta 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tabella di riepilogo del firewall di porta interna

|**Protocollo**|**TCP o UDP**|**Porta**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Uno dei seguenti eseguire il servizio gateway XMPP:  <br/> • Front End Server  <br/> • Pool Front End  <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico XMPP in uscita dal servizio gateway XMPP in esecuzione nel front end server o nel pool Front end.  <br/> **Nota:** I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015 ma non sono più supportati in Skype for Business Server 2019. Per ulteriori informazioni, vedere [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Qualsiasi  <br/> • Director  <br/> • Pool di server Director  <br/> • Front End Server  <br/> • Pool Front End  <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico SIP in uscita dal server Director, dal pool di Director, dall'front-end o dal pool Front end all'interfaccia interna del server perimetrale.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interfaccia interna del server perimetrale  <br/> |Qualsiasi  <br/> • Director  <br/> • Pool di server Director  <br/> • Front End Server  <br/> • Pool Front End  <br/> |Traffico SIP in ingresso verso il server Director, il pool di Director, il front-end o il pool Front end dall'interfaccia interna del server perimetrale.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Qualsiasi  <br/> • Front End Server  <br/> • Ogni Front End Server  <br/>  nel pool Front End <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico Web Conferencing dal front end server o da ogni Front End Server (se si dispone di un pool Front End) all'interfaccia interna del server perimetrale.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Qualsiasi  <br/> • Front End Server  <br/> • Pool Front End  <br/> • Qualsiasi Survivable Branch Appliance che utilizza questo server perimetrale  <br/> • Qualsiasi Survivable Branch Server che utilizza questo server perimetrale  <br/> |Interfaccia interna del server perimetrale  <br/> |Autenticazione degli utenti A/V dal front end server o dal pool Front end o dal Survivable Branch Appliance o Survivable Branch Server, utilizzando il server perimetrale.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni e il Survivable Branch Appliance o il Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni e il Survivable Branch Appliance o il Survivable Branch Server, se la comunicazione UDP non funziona. TCP viene quindi utilizzato per i trasferimenti di file e la condivisione del desktop.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Qualsiasi  <br/> • Front End Server che contiene l'archivio di gestione centrale  <br/> • Pool Front end che contiene l'archivio di gestione centrale  <br/> |Interfaccia interna del server perimetrale  <br/> |Replica delle modifiche apportate dall'archivio di gestione centrale al server perimetrale.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller del servizio di registrazione centralizzato con Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e raccolta di registri.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller del servizio di registrazione centralizzato con Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e raccolta di registri.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller del servizio di registrazione centralizzato con Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e raccolta di registri.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Dispositivi di bilanciamento del carico hardware per le tabelle delle porte perimetrali

Vengono conferiti ai servizi di bilanciamento del carico hardware (HLBs) e alle porte del perimetro la propria sezione, in quanto le cose sono un po' più complicate con l'hardware aggiuntivo. Fare riferimento alle tabelle riportate di seguito per informazioni dettagliate su questo scenario specifico:
  
#### <a name="external-port-firewall-summary-table"></a>Tabella di riepilogo del firewall per le porte esterne

L'indirizzo IP di origine e l'indirizzo IP di destinazione conterranno informazioni per gli utenti che utilizzano indirizzi IP privati con NAT, nonché persone che utilizzano indirizzi IP pubblici. Questo coprirà tutte le permutazioni negli [scenari del server perimetrale nella sezione Skype for Business Server](scenarios.md) .
  
|**Ruolo o protocollo**|**TCP o UDP**|**Porta di destinazione o intervallo di porte**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Accesso/HTTP  <br/> |TCP  <br/> |80  <br/> |Indirizzo IP pubblico del servizio Access Edge Server perimetrale  <br/> |Qualsiasi  <br/> |Revoca del certificato e controllo e recupero CRL.  <br/> |
|Accesso/DNS  <br/> |TCP  <br/> |53  <br/> |Indirizzo IP pubblico del servizio Access Edge Server perimetrale  <br/> |Qualsiasi  <br/> |Query DNS su TCP.  <br/> |
|Accesso/DNS  <br/> |UDP  <br/> |53  <br/> |Indirizzo IP pubblico del servizio Access Edge Server perimetrale  <br/> |Qualsiasi  <br/> |Query DNS su UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Indirizzo IP del servizio A/V Edge Server perimetrale  <br/> |Qualsiasi  <br/> |Viene utilizzato per l'inoltro del traffico multimediale.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Indirizzo IP pubblico del servizio A/V Edge Server perimetrale  <br/> |Qualsiasi  <br/> |Viene utilizzato per l'inoltro del traffico multimediale.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indirizzo IP pubblico del servizio A/V Edge Server perimetrale  <br/> |Qualsiasi  <br/> |3478 in uscita è:  <br/> • Utilizzato da Skype for Business Server per determinare la versione del server perimetrale che comunica con.  <br/> • Utilizzato per il traffico multimediale tra server perimetrali.  <br/> • Obbligatorio per la Federazione.  <br/> • Necessario se sono distribuiti più pool di server perimetrali all'interno dell'organizzazione.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> |Indirizzo IP pubblico del servizio A/V Edge Server perimetrale  <br/> |Negoziazione STUN/turno dei candidati su UDP sulla porta 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |Indirizzo IP pubblico del servizio A/V Edge Server perimetrale  <br/> |Negoziazione STUN/turno dei candidati su TCP sulla porta 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Indirizzo IP pubblico del servizio A/V Edge Server perimetrale  <br/> |Qualsiasi  <br/> |Negoziazione STUN/turno dei candidati su TCP sulla porta 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tabella di riepilogo del firewall di porta interna

|**Protocollo**|**TCP o UDP**|**Porta**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Uno dei seguenti eseguire il servizio gateway XMPP:  <br/> • Front End Server  <br/> • Indirizzo VIP del pool Front end in cui è in esecuzione il servizio gateway XMPP  <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico XMPP in uscita dal servizio gateway XMPP in esecuzione nel front end server o nel pool Front end.  <br/><br/> **Nota:** I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015 ma non sono più supportati in Skype for Business Server 2019. Per ulteriori informazioni, vedere [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Qualsiasi  <br/> • Front End Server che contiene l'archivio di gestione centrale  <br/> • Pool Front end che contiene l'archivio di gestione centrale  <br/> |Interfaccia interna del server perimetrale  <br/> |Replica delle modifiche apportate dall'archivio di gestione centrale al server perimetrale.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Qualsiasi  <br/> • Front End Server  <br/> • Ogni Front End Server nel pool Front End  <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico Web Conferencing dal front end server o da ogni Front End Server (se si dispone di un pool Front End) all'interfaccia interna del server perimetrale.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> • Front End Server  <br/> • Ogni Front End Server nel pool Front End  <br/> |Interfaccia interna del server perimetrale  <br/> |Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni e il Survivable Branch Appliance o il Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> • Front End Server  <br/> • Ogni Front End Server nel pool  <br/> |Interfaccia interna del server perimetrale  <br/> |Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni e il Survivable Branch Appliance o il Survivable Branch Server, se la comunicazione UDP non funziona. TCP viene quindi utilizzato per i trasferimenti di file e la condivisione del desktop.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller del servizio di registrazione centralizzato con Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e raccolta di registri.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller del servizio di registrazione centralizzato con Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e raccolta di registri.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller del servizio di registrazione centralizzato con Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e raccolta di registri.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>Indirizzi IP virtuali dell'interfaccia esterna

|**Ruolo o protocollo**|**TCP o UDP**|**Porta di destinazione o intervallo di porte**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Non supportato in Skype for Businesss server 2019 |TCP  <br/> |5269  <br/> |Qualsiasi  <br/> |Servizio proxy XMPP (condivide un indirizzo IP con il servizio Access Edge)  <br/> |Il servizio proxy XMPP accetta il traffico proveniente dai contatti XMPP nelle federazioni XMPP definite.  <br/> |
|XMPP  <br/>Non supportato in Skype for Businesss server 2019 |TCP  <br/> |5269  <br/> |Servizio proxy XMPP (condivide un indirizzo IP con il servizio Access Edge)  <br/> |Qualsiasi  <br/> |Il servizio proxy XMPP invia il traffico dai contatti XMPP nelle federazioni XMPP definite.  <br/> |
|Accesso/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio Access Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Access Edge Server perimetrale <br/> |Traffico SIP da client a server per l'accesso degli utenti esterni.  <br/> |
|Accesso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio Access Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Access Edge Server perimetrale <br/> |Per la connettività di messaggistica istantanea pubblica e federata con SIP.  <br/> |
|Accesso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privato tramite NAT:** Servizio Access Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Access Edge Server perimetrale <br/> |Qualsiasi  <br/> |Per la connettività di messaggistica istantanea pubblica e federata con SIP.  <br/> |
|Web Conferencing/PSOM (TLS)  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio Web Conferencing Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Web Conferencing Edge Server perimetrale <br/> |Supporto per Web Conferencing.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio A/V Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio A/V Edge Server perimetrale <br/> |Negoziazione STUN/turno dei candidati su UDP sulla porta 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio A/V Edge Server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio A/V Edge Server perimetrale <br/> |Negoziazione STUN/turno dei candidati su TCP sulla porta 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>IPs virtuale dell'interfaccia interna

La nostra guida qui sarà un po' diversa. In realtà, in una situazione di HLB, si consiglia di utilizzare solo il routing tramite un VIP interno nelle seguenti circostanze:
  
- Se si utilizza la messaggistica unificata di Exchange 2007 o Exchange 2010.
    
- Se si dispone di client legacy che utilizzano il server perimetrale.
    
Nella tabella seguente vengono fornite indicazioni per tali scenari, ma in caso contrario, è necessario essere in grado di dipendere dall'archivio di gestione centrale (CMS) per instradare il traffico verso i singoli server perimetrali di cui è a conoscenza (è necessario che il CMS sia mantenuto aggiornato sulle informazioni sui server perimetrali, ovviamente).
  
|**Protocollo**|**TCP o UDP**|**Porta**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Accesso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualsiasi  <br/> • Director  <br/> • Indirizzo VIP del pool di server Director  <br/> • Front End Server  <br/> • Indirizzo VIP del pool Front End  <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico SIP in uscita dal server Director, dall'indirizzo VIP del pool di Director, dall'indirizzo VIP di front end o dal pool Front end all'interfaccia interna del server perimetrale.  <br/> |
|Accesso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interfaccia VIP interna del server perimetrale  <br/> |Qualsiasi  <br/> • Director  <br/> • Indirizzo VIP del pool di server Director  <br/> • Front End Server  <br/> • Indirizzo VIP del pool Front End  <br/> |Traffico SIP in ingresso verso il server Director, l'indirizzo VIP del pool di server Director, l'indirizzo VIP di front-end o il pool Front end dall'interfaccia interna.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Qualsiasi  <br/> • Indirizzo IP di front end server  <br/> • Indirizzo IP del pool Front End  <br/> • Qualsiasi Survivable Branch Appliance che utilizza questo server perimetrale  <br/> • Qualsiasi Survivable Branch Server che utilizza questo server perimetrale  <br/> |Interfaccia interna del server perimetrale  <br/> |Autenticazione degli utenti A/V dal front end server o dal pool Front end o dal Survivable Branch Appliance o Survivable Branch Server, utilizzando il server perimetrale.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |Interfaccia VIP interna del server perimetrale  <br/> |Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni se la comunicazione UDP non funziona. TCP viene quindi utilizzato per i trasferimenti di file e la condivisione del desktop.  <br/> |
