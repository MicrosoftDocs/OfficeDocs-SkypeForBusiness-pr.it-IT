---
title: Requisiti ambientali dei server perimetrali in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Riepilogo: informazioni sui requisiti ambientali per il server perimetrale in Skype for Business Server.'
ms.openlocfilehash: 3757a67d36260cce7d14ddf451a3a436429f24fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813836"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Requisiti ambientali dei server perimetrali in Skype for Business Server
 
**Riepilogo:** Informazioni sui requisiti ambientali per il server perimetrale in Skype for Business Server.
  
È necessario eseguire molte attività di pianificazione e preparazione al di fuori dell'ambiente del server perimetrale di Skype for Business Server. In questo articolo verranno esaminati i preparativi da eseguire nell'ambiente dell'organizzazione, come indicato nell'elenco seguente:
  
- [Pianificazione della topologia](edge-environmental-requirements.md#TopoPlan)
    
- [Pianificazione dns](edge-environmental-requirements.md#DNSPlan)
    
- [Pianificazione dei certificati](edge-environmental-requirements.md#CertPlan)
    
- [Pianificazione di porte e firewall](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Pianificazione della topologia
<a name="TopoPlan"> </a>

Le topologie dei server perimetrali di Skype for Business Server sono in grado di utilizzare:
  
- Indirizzi IP pubblici instradabili.
    
- Indirizzi IP privati non instradabili, se viene utilizzato NAT **(Symmetric** Network Address Translation).
    
> [!TIP]
> Il server perimetrale può essere configurato per l'utilizzo di un singolo indirizzo IP con porte distinte per ogni servizio oppure può utilizzare indirizzi IP distinti per ogni servizio, ma utilizzare la stessa porta predefinita (che per impostazione predefinita sarà TCP 443). Di seguito sono disponibili ulteriori informazioni nella sezione requisiti degli indirizzi IP. 
  
Se si scelgono indirizzi IP privati non instradabili con NAT, ricordare questi punti:
  
- È necessario utilizzare indirizzi IP privati instradabili su **tutte e tre** le interfacce esterne.
    
- È necessario configurare NAT **simmetrico per** il traffico in ingresso e in uscita. Nat simmetrico è l'unico NAT supportato che è possibile utilizzare con Skype for Business Server Edge Server.
    
- Configurare nat in modo da non modificare gli indirizzi di origine in ingresso. Il servizio A/V Edge deve essere in grado di ricevere l'indirizzo di origine in ingresso per trovare il percorso multimediale ottimale.
    
- I server perimetrali devono essere in grado di comunicare tra loro dagli indirizzi IP A/V Edge pubblici. Il firewall deve consentire questo traffico.
    
- NAT può **essere utilizzato** solo per i server perimetrali consolidati con scalabilità orizzontale se si utilizza il bilanciamento del carico DNS. Se si utilizza il bilanciamento del carico hardware (HLB), è necessario utilizzare indirizzi IP instradabili pubblicamente **senza** NAT.
    
Le interfacce Access, Web Conferencing e A/V Edge sono dietro un router o un firewall che esegue nat simmetrico sia per topologie di server perimetrali consolidati con scalabilità implementata che per topologie di server perimetrali consolidati con scalabilità implementata (purché non si utilizzi il bilanciamento del carico hardware).
  
### <a name="summary-of-edge-server-topology-options"></a>Riepilogo delle opzioni di topologia dei server perimetrali

Sono disponibili diverse opzioni di topologia per le distribuzioni di Server perimetrali di Skype for Business Server:
  
- Singola topologia perimetrale consolidata con indirizzi IP privati e NAT
    
- Singola topologia perimetrale consolidata con indirizzi IP pubblici
    
- Topologia perimetrale consolidata con scalabilità orizzontale con indirizzi IP privati e NAT
    
- Topologia perimetrale consolidata con scalabilità orizzontale con indirizzi IP pubblici
    
- Topologia perimetrale consolidata con scalabilità orizzontale con servizi di bilanciamento del carico hardware
    
Per facilitare la scelta, è riportata la tabella seguente che fornisce un riepilogo delle opzioni disponibili per ogni topologia:
  
|**Topologia**|**Disponibilità elevata**|**Record DNS aggiuntivi necessari per il server perimetrale esterno nel pool di server perimetrali?**|**Failover edge per le sessioni di Skype for Business Server**|**Failover edge per le sessioni di federazione di Skype for Business Server**|
|:-----|:-----|:-----|:-----|:-----|
|Singola topologia perimetrale consolidata con indirizzi IP privati e NAT  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Singola topologia perimetrale consolidata con indirizzi IP pubblici  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Topologia perimetrale consolidata con scalabilità orizzontale con indirizzi IP privati e NAT (bilanciamento del carico DNS)  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì&sup1;  <br/> |
|Topologia perimetrale consolidata con scalabilità orizzontale con indirizzi IP pubblici (bilanciamento del carico DNS)  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì&sup1;  <br/> |
|Topologia perimetrale consolidata con scalabilità orizzontale con servizi di bilanciamento del carico hardware  <br/> |Sì  <br/> |No (un record A DNS per IP virtuale)  <br/> |Sì  <br/> |Sì  <br/> |
   
&sup1; Il failover degli utenti remoti di messaggistica unificata di Exchange utilizzando il bilanciamento del carico DNS richiede Exchange 2013 o versione più recente.
  
### <a name="ip-address-requirements"></a>Requisiti degli indirizzi IP

A livello fondamentale, tre servizi necessitano di indirizzi IP; Servizio Access Edge, servizio Web Conferencing Edge e servizio A/V Edge. È possibile scegliere di utilizzare tre indirizzi IP, uno per ognuno dei servizi, oppure di sceglierne uno e scegliere di inserire ogni servizio su una porta diversa (per altre informazioni, vedere la sezione Relativa alla pianificazione di porte e [firewall).](edge-environmental-requirements.md#PortFirewallPlan) Per un singolo ambiente perimetrale consolidato, è praticamente tutto.
  
> [!NOTE]
> Come indicato in precedenza, è possibile scegliere di avere un indirizzo IP per tutti e tre i servizi ed eseguirli su porte diverse. Tuttavia, è sconsigliato. Se i clienti non possono accedere alle porte alternative che si usano in questo scenario, non possono accedere alle funzionalità complete dell'ambiente Edge. 
  
Può essere un po' più complicato con topologie consolidate con scalabilità implementata, quindi esaminiamo alcune tabelle in cui sono riportati i requisiti degli indirizzi IP, tenendo presente che la decisione principale per la selezione della topologia è la disponibilità elevata e il bilanciamento del carico. Le esigenze di disponibilità elevata possono influire sulla scelta del bilanciamento del carico (ne parleremo di più dopo le tabelle).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisiti degli indirizzi IP per server perimetrale consolidato con scalabilità orizzontale (indirizzo IP per ruolo)

|**Numero di server perimetrali per pool**|**Numero di indirizzi IP necessari per il bilanciamento del carico DNS**|**Numero di indirizzi IP necessari per il bilanciamento del carico hardware**|
|:-----|:-----|:-----|
|2   <br/> |6   <br/> |3 (1 per VIP) + 6  <br/> |
|3   <br/> |9   <br/> |3 (1 per VIP) + 9  <br/> |
|4   <br/> |12   <br/> |3 (1 per VIP) + 12  <br/> |
|5   <br/> |15   <br/> |3 (1 per VIP) +15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Requisiti degli indirizzi IP per server perimetrale consolidato con scalabilità orizzontale (indirizzo IP singolo per tutti i ruoli)

|**Numero di server perimetrali per pool**|**Numero di indirizzi IP necessari per il bilanciamento del carico DNS**|**Numero di indirizzi IP necessari per il bilanciamento del carico hardware**|
|:-----|:-----|:-----|
|2   <br/> |2   <br/> |1 (1 per IP virtuale) + 2  <br/> |
|3   <br/> |3   <br/> |3 (1 per IP virtuale) + 6  <br/> |
|4   <br/> |4   <br/> |4 (1 per IP virtuale) + 6  <br/> |
|5   <br/> |5   <br/> |5 (1 per IP virtuale) + 6  <br/> |
   
Esaminiamo alcuni aspetti aggiuntivi da riflettere durante la pianificazione.
  
- **Disponibilità elevata:** se è necessaria una disponibilità elevata nella distribuzione, è necessario distribuire almeno due server perimetrali in un pool. Vale la pena notare che un singolo pool di server perimetrali supporterà fino a 12 server perimetrali (anche se Generatore di topologie consentirà di sommare fino a 20, non testati o supportati, quindi si consiglia di non farlo). Se sono necessari più di 12 server perimetrali, è necessario creare ulteriori pool di server perimetrali.
    
- **Bilanciamento del carico hardware:** è consigliabile il bilanciamento del carico DNS per la maggior parte degli scenari. Naturalmente è supportato anche il bilanciamento del carico hardware, ma in particolare è necessario per un singolo scenario rispetto al bilanciamento del carico DNS:
    
  - Accesso esterno alla messaggistica unificata di Exchange 2007 o Exchange 2010 (senza SP).
    
- **Bilanciamento del carico DNS:** per la messaggistica unificata, Exchange 2010 SP1 e versioni più nuove possono essere supportati dal bilanciamento del carico DNS. Tenere presente che se è necessario utilizzare il bilanciamento del carico DNS per una versione precedente di Exchange, funzionerà, ma tutto il traffico per questa operazione verrà eseguito sul primo server del pool e, se non è disponibile, il traffico avrà esito negativo.
    
    Il bilanciamento del carico DNS è consigliato anche se si sta federazionendo con società che utilizzano:
- Skype for Business Server 2015:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft 365 o Office 365
- Skype for Business Server 2019:
    - Lync Server 2013
    - Skype for Business Server 2015
    - Microsoft 365 o Office 365
    
## <a name="dns-planning"></a>Pianificazione dns
<a name="DNSPlan"> </a>

Per quanto riguarda la distribuzione di Server perimetrali di Skype for Business Server, è fondamentale prepararsi correttamente per DNS. Con i record a posto, la distribuzione sarà molto più semplice. È possibile che sia stata scelta una topologia nella sezione precedente, poiché verrà fornita una panoramica e quindi saranno elencate alcune tabelle che delineano i record DNS per tali scenari. Per una lettura più approfondita, se necessario, sarà disponibile anche una pianificazione DNS di Advanced Edge Server per [Skype for Business Server.](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md)
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>Record DNS per scenari di server perimetrali consolidati singoli

Questi saranno i record DNS necessari per un server perimetrale di singe usando ip pubblici o ip privati con NAT. Poiché si tratta di dati di esempio, verranno creati indirizzi IP di esempio in modo da poter gestire le proprie voci più facilmente:
  
- Scheda di rete interna: 172.25.33.10 (nessun gateway predefinito assegnato)
    
    > [!NOTE]
    > Verificare che sia presente una route dalla rete contenente l'interfaccia interna perimetrale a tutte le reti contenenti server che eseguono i client Skype for Business Server o Lync Server 2013 (ad esempio, da 172.25.33.0 a 192.168.10.0). 
  
- Scheda di rete esterna:
    
  - IP pubblici:
    
  - Access Edge: 131.107.155.10 (questo è il principale, con il gateway predefinito impostato sul router pubblico, ad esempio: 131.107.155.1)
    
  - Web Conferencing Edge: 131.107.155.20 (secondario)
    
  - A/V Edge: 131.107.155.30 (secondario)
    
  Gli indirizzi IP pubblici di Web Conferencing e A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà di Internet Protocol version 4 (TCP/IPv4) e Internet Protocol version 6 (TCP/IPv6) delle proprietà di Connessione alla rete locale (LAN) in Windows Server.
    
  - IP privati:
    
  - Access Edge: 10.45.16.10 (questo è il principale, con il gateway predefinito impostato sul router, ad esempio: 10.45.16.1)
    
  - Web Conferencing Edge: 10.45.16.20 (secondario)
    
  - A/V Edge: 10.45.16.30 (secondario)
    
Gli indirizzi IP pubblici di Web Conferencing e A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà di Internet Protocol version 4 (TCP/IPv4) e Internet Protocol version 6 (TCP/IPv6) delle proprietà di Connessione alla rete locale (LAN) in Windows Server.
  
> [!TIP]
>Di seguito sono disponibili altre configurazioni possibili:
  
- È possibile utilizzare un solo indirizzo IP nella scheda di rete esterna. Non è consigliabile, perché sarà necessario distinguere i servizi con porte diverse (operazione che è possibile eseguire in Skype for Business Server), ma esistono alcuni firewall che potrebbero bloccare le porte alternative. Per ulteriori [informazioni, vedere](edge-environmental-requirements.md#PortFirewallPlan) la sezione Relativa alla pianificazione di porte e firewall.
    
- È possibile disporre di tre schede di rete esterne anziché di una e assegnare uno degli IP di servizio a ognuna di queste. Perché eseguire questa operazione? Se si verifica un problema, i servizi vengono separati e, in caso di problemi, la risoluzione dei problemi risulta più semplice e gli altri servizi potrebbero continuare a funzionare mentre si risolve un problema.
    
|**Posizione**|**Type**|**Porta**|**FQDN o record DNS**|**Indirizzo IP o FQDN**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS esterno  <br/> |Un record  <br/> |ND  <br/> |sip.contoso.com  <br/> |**public:** 131.107.155.10 <br/> **private:** 10.45.16.10 <br/> |Un'interfaccia esterna per il servizio Access Edge. Ne sarà necessario uno per ogni dominio SIP con utenti di Skype for Business.  <br/> |
|DNS esterno  <br/> |Un record  <br/> |ND  <br/> |webcon.contoso.com  <br/> |**public:** 131.107.155.20 <br/> **private:** 10.45.16.20 <br/> |Un'interfaccia esterna per il servizio Web Conferencing Edge.  <br/> |
|DNS esterno  <br/> |Un record  <br/> |ND  <br/> |av.contoso.com  <br/> |**public:** 131.107.155.30 <br/> **private:** 10.45.16.30 <br/> |Un'interfaccia esterna per il servizio A/V Edge.  <br/> |
|DNS esterno  <br/> |record SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Un'interfaccia esterna per il servizio Access Edge. Questo record SRV è necessario per il funzionamento esterno dei client Skype for Business Server, Lync Server 2013 e Lync Server 2010. You'll need one for every domain with Skype for Business users.  <br/> |
|DNS esterno  <br/> |record SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Un'interfaccia esterna per il servizio Access Edge. Questo record SRV è necessario per l'individuazione DNS automatica di partner federati denominati domini SIP consentiti. You'll need one for every domain with Skype for Business users.  <br/> |
|DNS interno  <br/> |Un record  <br/> |ND  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |L'interfaccia interna per il server perimetrale consolidato.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>Record DNS per scenari di server perimetrali hardware e DNS con scalabilità verticale

Questi saranno i record DNS necessari per un server perimetrale di singe usando ip pubblici o ip privati con NAT. Poiché si tratta di dati di esempio, verranno creati indirizzi IP di esempio in modo da poter gestire le proprie voci più facilmente:
  
- Scheda di rete interna:
    
  - Nodo 1: 172.25.33.10 (nessun gateway predefinito assegnato)
    
  - Nodo 2: 172.25.33.11 (nessun gateway predefinito assegnato)
    
    > [!NOTE]
    > Verificare che sia presente una route dalla rete contenente l'interfaccia interna perimetrale a tutte le reti contenenti server che eseguono i client Skype for Business Server o Lync Server 2013 (ad esempio, da 172.25.33.0 a 192.168.10.0). 
  
- Scheda di rete esterna:
    
  - Nodo 1
    
     - IP pubblici:
    
        - Access Edge: 131.107.155.10 (questo è il principale, con il gateway predefinito impostato sul router pubblico, ad esempio: 131.107.155.1)
    
        - Web Conferencing Edge: 131.107.155.20 (secondario)
    
        - A/V Edge: 131.107.155.30 (secondario)
    
          Gli indirizzi IP pubblici di Web Conferencing e A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà di Internet Protocol version 4 (TCP/IPv4) e Internet Protocol version 6 (TCP/IPv6) delle proprietà di Connessione alla rete locale (LAN) in Windows Server.
    
    - IP privati:
    
         - Access Edge: 10.45.16.10 (questo è il principale, con il gateway predefinito impostato sul router, ad esempio: 10.45.16.1)
    
         - Web Conferencing Edge: 10.45.16.20 (secondario)
    
         - A/V Edge: 10.45.16.30 (secondario)
    
      Gli indirizzi IP pubblici di Web Conferencing e A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà di Internet Protocol version 4 (TCP/IPv4) e Internet Protocol version 6 (TCP/IPv6) delle proprietà di Connessione alla rete locale (LAN) in Windows Server.
    
  - Nodo 2
    
    - IP pubblici:
    
      - Access Edge: 131.107.155.11 (questo è il principale, con il gateway predefinito impostato sul router pubblico, ad esempio: 131.107.155.1)
    
      - Web Conferencing Edge: 131.107.155.21 (secondario)
    
      - A/V Edge: 131.107.155.31 (secondario)
    
      Gli indirizzi IP pubblici di Web Conferencing e A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà di Internet Protocol version 4 (TCP/IPv4) e Internet Protocol version 6 (TCP/IPv6) delle proprietà di Connessione alla rete locale (LAN) in Windows Server.
    
  - IP privati:
    
    - Access Edge: 10.45.16.11 (questo è il principale, con il gateway predefinito impostato sul router, ad esempio: 10.45.16.1)
    
    - Web Conferencing Edge: 10.45.16.21 (secondario)
    
    - A/V Edge: 10.45.16.31 (secondario)
    
      Gli indirizzi IP pubblici di Web Conferencing e A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà di Internet Protocol version 4 (TCP/IPv4) e Internet Protocol version 6 (TCP/IPv6) delle proprietà di Connessione alla rete locale (LAN) in Windows Server.
    
Di seguito sono disponibili altre configurazioni possibili:
  
- È possibile utilizzare un solo indirizzo IP nella scheda di rete esterna. Non è consigliabile, perché sarà necessario distinguere i servizi con porte diverse (operazione che è possibile eseguire in Skype for Business Server), ma esistono alcuni firewall che potrebbero bloccare le porte alternative. Per ulteriori [informazioni, vedere](edge-environmental-requirements.md#PortFirewallPlan) la sezione Relativa alla pianificazione di porte e firewall.
    
- È possibile disporre di tre schede di rete esterne anziché di una e assegnare uno degli IP di servizio a ognuna di queste. Perché eseguire questa operazione? Se si verifica un problema, i servizi vengono separati e, in caso di problemi, la risoluzione dei problemi risulta più semplice e gli altri servizi potrebbero continuare a funzionare mentre si risolve un problema.
    
|**Posizione**|**Type**|**Porta**|**FQDN o record DNS**|**Indirizzo IP o FQDN**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS esterno  <br/> |Un record  <br/> |ND  <br/> |sip.contoso.com  <br/> |**public:** 131.107.155.10 e 131.107.155.11 <br/> **private:** 10.45.16.10 e 10.45.16.11 <br/> |Un'interfaccia esterna per il servizio Access Edge. Ne sarà necessario uno per ogni dominio SIP con utenti di Skype for Business.  <br/> |
|DNS esterno  <br/> |Un record  <br/> |ND  <br/> |webcon.contoso.com  <br/> |**public:** 131.107.155.20 e 131.107.155.21 <br/> **private:** 10.45.16.20 e 10.45.16.21 <br/> |Un'interfaccia esterna per il servizio Web Conferencing Edge.  <br/> |
|DNS esterno  <br/> |Un record  <br/> |ND  <br/> |av.contoso.com  <br/> |**public:** 131.107.155.30 e 131.107.155.31 <br/> **private:** 10.45.16.30 e 10.45.16.31 <br/> |Un'interfaccia esterna per il servizio A/V Edge.  <br/> |
|DNS esterno  <br/> |record SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Un'interfaccia esterna per il servizio Access Edge. Questo record SRV è necessario per il funzionamento esterno dei client Skype for Business Server, Lync Server 2013 e Lync Server 2010. Ne sarà necessario uno per ogni dominio con Skype for Business.  <br/> |
|DNS esterno  <br/> |record SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Un'interfaccia esterna per il servizio Access Edge. Questo record SRV è necessario per l'individuazione DNS automatica di partner federati denominati domini SIP consentiti. Ne sarà necessario uno per ogni dominio con Skype for Business.  <br/> |
|DNS interno  <br/> |Un record  <br/> |ND  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 e 172.25.33.11  <br/> |L'interfaccia interna per il server perimetrale consolidato.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Record DNS per la federazione (tutti gli scenari)

|**Posizione**|**Type**|**Porta**|**FQDN**|**Record host FQDN**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS esterno  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Interfaccia esterna access edge SIP necessaria per l'individuazione DNS automatica. Utilizzato dagli altri potenziali partner federativi. È noto anche come "Consenti domini SIP". You'll need one of these for each SIP domain with Skype for Business users.  <br/><br/> **Nota:** Sarà necessario questo record SRV per i dispositivi mobili e il centro di cancellazione delle notifiche push. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Record DNS per il protocollo di messaggistica e presenza estensibile

|**Posizione**|**Type**|**Porta**|**FQDN**|**Indirizzo IP o record host FQDN**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS esterno  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |L'interfaccia proxy XMPP nel servizio Access Edge o nel pool di server perimetrali. È necessario ripetere questa operazione in base alle esigenze per tutti i domini SIP interni con utenti abilitati per Skype for Business Server, in cui il contatto con i contatti XMPP è consentito tramite:  <br/> • un criterio globale  <br/> • Un criterio sito in cui l'utente è abilitato  <br/> • Un criterio utente applicato all'utente abilitato per Skype for Business Server  <br/> È inoltre necessario configurare un criterio XMPP consentito nei criteri degli utenti federati XMPP.  <br/> |
|DNS esterno  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |Indirizzo IP del servizio Access Edge nel server perimetrale o nel pool di server perimetrali che ospita il servizio proxy XMPP  <br/> |Questo punta al servizio Access Edge nel server perimetrale o nel pool di server perimetrali che ospita il servizio proxy XMPP. In genere il record SRV creato farà riferimento a questo record host (A o AAAA).  <br/> |
   
> [!NOTE]
> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per [ulteriori informazioni, vedere Migrating XMPP federation.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)

## <a name="certificate-planning"></a>Pianificazione dei certificati
<a name="CertPlan"> </a>

Skype for Business Server usa i certificati per comunicazioni protette e crittografate sia tra server che da server a client. Come previsto, i certificati dovranno disporre di record DNS per i server corrispondenti a qualsiasi nome soggetto (SN) e nome alternativo soggetto (SAN) nei certificati. A questo punto, nella fase di pianificazione, sarà necessario verificare di avere i nomi FQDN necessari registrati in DNS per le voci SN e SAN per i certificati.
  
Verranno descritte separatamente le esigenze dei certificati interni ed esterni, quindi verrà analizzata una tabella che fornisce i requisiti per entrambi.
  
### <a name="external-certificates"></a>Certificati esterni

Come minimo, il certificato assegnato alle interfacce dei server perimetrali esterni dovrà essere fornito da un'autorità di certificazione (CA) pubblica. Non è possibile consigliare un'autorità di certificazione specifica, ma è disponibile un elenco di CA, partner di certificati [per](/SkypeForBusiness/certification/services-ssl) comunicazioni unificate, che è possibile esaminare per verificare se l'autorità di certificazione preferita è elencata.
  
Quando sarà necessario inviare una richiesta a un'autorità di certificazione per questo certificato pubblico e come procedere? Esistono due modi per eseguire questa operazione:
  
- È possibile eseguire l'installazione di Skype for Business Server e quindi la distribuzione del server perimetrale. La Distribuzione guidata di Skype for Business Server avrà un passaggio per generare una richiesta di certificato, che sarà quindi possibile inviare alla CA scelta.
    
- Puoi anche usare i Windows PowerShell per generare questa richiesta, se questo è più in linea con le esigenze aziendali o la strategia di distribuzione.
    
- Infine, l'autorità di certificazione potrebbe avere un proprio processo di invio, che può anche coinvolgere Windows PowerShell o un altro metodo. In questo caso, dovrai fare affidamento sulla documentazione, oltre alle informazioni qui fornite per riferimento.
    
Dopo aver ottenuto il certificato, dovrai procedere e assegnarlo a questi servizi in Skype for Business Server:
  
- Interfaccia del servizio Access Edge
    
- Interfaccia del servizio Web Conferencing Edge
    
- Servizio di autenticazione audio/video (non confondere questo servizio con il servizio A/V Edge, perché non usa un certificato per crittografare flussi audio e video)
    
> [!IMPORTANT]
> Tutti i server perimetrali (se appartengono allo stesso pool di server perimetrali) devono disporre dello stesso certificato con la stessa chiave privata per il servizio Di autenticazione Media Relay. 
  
### <a name="internal-certificates"></a>Certificati interni

Per l'interfaccia del server perimetrale interno, è possibile utilizzare un certificato pubblico di una CA pubblica o un certificato emesso dalla CA interna dell'organizzazione. È importante ricordare che il certificato interno utilizza una voce SN e nessuna voce SAN, quindi non è necessario preoccuparsi di SAN nel certificato interno.
  
### <a name="required-certificates-table"></a>Tabella Certificati obbligatori

Di seguito è riportata una tabella per aiutarti con le tue richieste. Le voci FQDN qui presenti sono solo per i domini di esempio. Dovrai effettuare richieste in base ai tuoi domini privati e pubblici, ma ecco una guida a ciò che abbiamo usato:
  
- contoso <span></span> .com: FQDN pubblico
    
- fabrikam .com: secondo FQDN pubblico (aggiunto come dimostrazione di cosa richiedere <span></span> se si dispone di più domini SIP)
    
- Contoso <span></span> .net: dominio interno
    
#### <a name="edge-certificate-table"></a>Tabella Edge Certificate

Indipendentemente dal fatto che si stia eseguendo un singolo server perimetrale o un pool di server perimetrali, questo è ciò che ti serve per il certificato:
  
|**Componente**|**Nome soggetto (SN)**|**Nomi alternativi del soggetto (SAN)/ordine**|**Note**|
|:-----|:-----|:-----|:-----|
|Perimetro esterno  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Si tratta del certificato che è necessario richiedere a un'autorità di certificazione pubblica. Sarà necessario assegnarla alle interfacce perimetrali esterne per gli elementi seguenti:  <br/> • Access Edge  <br/> • Web Conferencing Edge  <br/> • Autenticazione audio/video  <br/> <br/>La buona notizia è che le reti SAN vengono aggiunte automaticamente alla richiesta di certificato e quindi il certificato dopo l'invio della richiesta, in base a quanto definito per questa distribuzione in Generatore di topologie. Sarà necessario aggiungere solo voci SAN per eventuali domini SIP aggiuntivi o altre voci che è necessario supportare. Perché la sip.contoso.com replica in questa istanza? Ciò avviene automaticamente ed è necessario per il corretto funzionamento.  <br/><br/> **Nota:** Questo certificato può essere utilizzato anche per la connettività di messaggistica istantanea pubblica. Non è necessario eseguire operazioni diverse, ma nelle versioni precedenti di questa documentazione è stata elencata come tabella separata e ora non lo è. <br/> |
|Perimetro interno  <br/> |sfbedge.contoso.com  <br/> |ND  <br/> |È possibile ottenere questo certificato da una CA pubblica o interna. Sarà necessario contenere l'EKU del server (Utilizzo chiavi avanzato) e assegnarlo all'interfaccia perimetrale interna.  <br/> |
   
Se è necessario un certificato per XMPP (Extensible Messaging and Presence Protocol), l'aspetto sarà identico a quello delle voci precedenti della tabella Dei server perimetrali esterni, ma con le due voci SAN aggiuntive seguenti:
  
- xmpp. <span></span> contoso <span></span> .com
    
- \*.contoso <span></span> .com
    
Ricorda che attualmente XMPP è supportato solo in Skype for Business Server per Google Talk, se vuoi o devi usarlo per qualsiasi altra cosa, devi confermare questa funzionalità con il fornitore di terze parti coinvolto.
  
## <a name="port-and-firewall-planning"></a>Pianificazione di porte e firewall
<a name="PortFirewallPlan"> </a>

Ottenere la pianificazione giusta per le porte e i firewall per le distribuzioni di Server perimetrali di Skype for Business Server consente di risparmiare giorni o settimane di risoluzione dei problemi e stress. Di conseguenza, verranno elencate un paio di tabelle che indicheranno l'utilizzo del protocollo e le porte necessarie per aprire, in ingresso e in uscita, per gli scenari NAT e IP pubblici. Saranno inoltre disponibili tabelle separate per gli scenari con bilanciamento del carico hardware (HLB) e alcune indicazioni aggiuntive su tale scenario. Per altre informazioni, abbiamo anche alcuni scenari di server perimetrali [in Skype for Business Server](scenarios.md) che puoi consultare per informazioni specifiche sulla distribuzione.
  
### <a name="general-protocol-usage"></a>Utilizzo generale del protocollo

Prima di esaminare le tabelle di riepilogo per i firewall esterni ed interni, prendere in considerazione anche la tabella seguente:
  
|**Trasporto audio/video**|**Usage**|
|:-----|:-----|
|UDP  <br/> |Protocollo del livello di trasporto preferito per audio e video.  <br/> |
|TCP  <br/> |Protocollo del livello di trasporto di fallback per audio e video.  <br/> Protocollo del livello di trasporto necessario per la condivisione delle applicazioni con Skype for Business Server, Lync Server 2013 e Lync Server 2010.  <br/> Protocollo del livello di trasporto necessario per il trasferimento di file in Skype for Business Server, Lync Server 2013 e Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tabella di riepilogo del firewall delle porte esterne

L'indirizzo IP di origine e l'indirizzo IP di destinazione conterranno informazioni per gli utenti che utilizzano indirizzi IP privati con NAT, nonché per gli utenti che utilizzano indirizzi IP pubblici. Verranno trattate tutte le permutazioni negli scenari [dei server perimetrali nella sezione Skype for Business Server.](scenarios.md)
  
|**Ruolo o protocollo**|**TCP o UDP**|**Porta di destinazione o intervallo di porte**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Non supportato in Skype for Business Server 2019 |TCP  <br/> |5269  <br/> |Qualsiasi  <br/> |Servizio proxy XMPP (condivide un indirizzo IP con il servizio Access Edge  <br/> |Il servizio proxy XMPP accetta il traffico dai contatti XMPP nelle federazioni XMPP definite.  <br/> |
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |**IP privato tramite NAT:** Servizio Edge server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge server perimetrale <br/> |Qualsiasi  <br/> |Revoca del certificato e controllo e recupero CRL.  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |**IP privato tramite NAT:** Servizio Edge server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge server perimetrale <br/> |Qualsiasi  <br/> |Query DNS su TCP.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |**IP privato tramite NAT:** Servizio Edge server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge server perimetrale <br/> |Qualsiasi  <br/> |Query DNS su UDP.  <br/> |
|Access/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio Edge server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge server perimetrale <br/> |Traffico SIP da client a server per l'accesso degli utenti esterni.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio Edge server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge server perimetrale <br/> |Per la connettività di messaggistica istantanea pubblica e federata tramite SIP.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privato tramite NAT:** Servizio Edge server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge server perimetrale <br/> |Qualsiasi  <br/> |Per la connettività di messaggistica istantanea pubblica e federata tramite SIP.  <br/> |
|Web Conferencing/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio Edge Server Web Conferencing Edge <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Web Conferencing Edge del server perimetrale <br/> |Contenuti multimediali per conferenze Web.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**IP privato tramite NAT:** Servizio Edge Server A/V Edge <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server A/V Edge <br/> |Qualsiasi  <br/> |Viene usato per l'inoltro del traffico multimediale.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**IP privato tramite NAT:** Servizio Edge Server A/V Edge <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server A/V Edge <br/> |Qualsiasi  <br/> |Viene usato per l'inoltro del traffico multimediale.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**IP privato tramite NAT:** Servizio Edge Server A/V Edge <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server A/V Edge <br/> |Qualsiasi  <br/> |3478 in uscita è:  <br/> • Usato da Skype for Business Server per determinare la versione del server perimetrale con cui comunica.  <br/> • Utilizzato per il traffico multimediale tra server perimetrali.  <br/> • Obbligatorio per la federazione con Lync Server 2010.  <br/> • Necessario se all'interno dell'organizzazione vengono distribuiti più pool di server perimetrali.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio Edge Server A/V Edge <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server A/V Edge <br/> |Negoziazione STUN/TURN dei candidati su UDP sulla porta 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio Edge Server A/V Edge <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server A/V Edge <br/> |Negoziazione STUN/TURN dei candidati su TCP sulla porta 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**IP privato tramite NAT:** Servizio Edge Server A/V Edge <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server A/V Edge <br/> |Qualsiasi  <br/> |Negoziazione STUN/TURN dei candidati su TCP sulla porta 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tabella di riepilogo del firewall delle porte interne

|**Protocollo**|**TCP o UDP**|**Porta**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Uno degli elementi seguenti che eseguono il servizio gateway XMPP:  <br/> • Front End Server  <br/> • Pool Front End  <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico XMPP in uscita dal servizio gateway XMPP in esecuzione nel Front End Server o nel pool Front End.  <br/> **Nota:** I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per [ulteriori informazioni, vedere Migrating XMPP federation.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Qualsiasi:  <br/> • Director  <br/> • Pool di server Director  <br/> • Front End Server  <br/> • Pool Front End  <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico SIP in uscita dal Director, dal pool di server Director, dal Front End Server o dal pool Front End all'interfaccia interna del server perimetrale.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interfaccia interna del server perimetrale  <br/> |Qualsiasi:  <br/> • Director  <br/> • Pool di server Director  <br/> • Front End Server  <br/> • Pool Front End  <br/> |Traffico SIP in ingresso verso il Director, il pool di server Director, il Front End Server o il pool Front End dall'interfaccia interna del server perimetrale.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Qualsiasi:  <br/> • Front End Server  <br/> • Ogni Front End Server  <br/>  nel pool Front End <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico di Conferenze Web dal Front End Server o da ogni Front End Server (se si dispone di un pool Front End) all'interfaccia interna del server perimetrale.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Qualsiasi:  <br/> • Front End Server  <br/> • Pool Front End  <br/> • Qualsiasi Survivable Branch Appliance che utilizza questo server perimetrale  <br/> • Qualsiasi Survivable Branch Server che utilizza questo server perimetrale  <br/> |Interfaccia interna del server perimetrale  <br/> |Autenticazione degli utenti A/V dal Front End Server o dal pool Front End oppure dal Survivable Branch Appliance o dal Survivable Branch Server utilizzando il server perimetrale.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Percorso preferito per il trasferimento di supporti A/V tra gli utenti interni ed esterni e il Survivable Branch Appliance o il Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Percorso di fallback per il trasferimento di supporti A/V tra gli utenti interni ed esterni e il Survivable Branch Appliance o il Survivable Branch Server, se la comunicazione UDP non funziona. TCP viene quindi utilizzato per i trasferimenti di file e la condivisione desktop.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Qualsiasi:  <br/> • Front End Server che contiene l'archivio di gestione centrale  <br/> • Pool Front End che contiene l'archivio di gestione centrale  <br/> |Interfaccia interna del server perimetrale  <br/> |Replica delle modifiche dall'archivio di gestione centrale al server perimetrale.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller del servizio di registrazione centralizzato tramite Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzata, comandi della riga di comando (ClsController.exe) o agente (ClsAgent.exe) e raccolta dei registri.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller del servizio di registrazione centralizzato tramite Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzata, comandi della riga di comando (ClsController.exe) o agente (ClsAgent.exe) e raccolta dei registri.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller del servizio di registrazione centralizzato tramite Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzata, comandi della riga di comando (ClsController.exe) o agente (ClsAgent.exe) e raccolta dei registri.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Servizi di bilanciamento del carico hardware per le tabelle delle porte perimetrali

Stiamo fornendo ai dispositivi di bilanciamento del carico hardware (HLB) e alle porte perimetrali la propria sezione, perché le cose sono un po' più complicate con l'hardware aggiuntivo. Fare riferimento alle tabelle seguenti per indicazioni su questo scenario specifico:
  
#### <a name="external-port-firewall-summary-table"></a>Tabella di riepilogo del firewall delle porte esterne

L'indirizzo IP di origine e l'indirizzo IP di destinazione conterranno informazioni per gli utenti che utilizzano indirizzi IP privati con NAT, nonché per gli utenti che utilizzano indirizzi IP pubblici. Verranno trattate tutte le permutazioni negli scenari [dei server perimetrali nella sezione Skype for Business Server.](scenarios.md)
  
|**Ruolo o protocollo**|**TCP o UDP**|**Porta di destinazione o intervallo di porte**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |Indirizzo IP pubblico del servizio Edge server perimetrale  <br/> |Qualsiasi  <br/> |Revoca del certificato e controllo e recupero CRL.  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |Indirizzo IP pubblico del servizio Edge server perimetrale  <br/> |Qualsiasi  <br/> |Query DNS su TCP.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |Indirizzo IP pubblico del servizio Edge server perimetrale  <br/> |Qualsiasi  <br/> |Query DNS su UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Indirizzo IP del servizio Edge Server A/V Edge  <br/> |Qualsiasi  <br/> |Viene usato per l'inoltro del traffico multimediale.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Indirizzo IP pubblico del servizio Edge Server A/V Edge  <br/> |Qualsiasi  <br/> |Viene usato per l'inoltro del traffico multimediale.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indirizzo IP pubblico del servizio Edge Server A/V Edge  <br/> |Qualsiasi  <br/> |3478 in uscita è:  <br/> • Usato da Skype for Business Server per determinare la versione del server perimetrale con cui comunica.  <br/> • Utilizzato per il traffico multimediale tra server perimetrali.  <br/> • Obbligatorio per la federazione.  <br/> • Necessario se all'interno dell'organizzazione vengono distribuiti più pool di server perimetrali.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> |Indirizzo IP pubblico del servizio Edge Server A/V Edge  <br/> |Negoziazione STUN/TURN dei candidati su UDP sulla porta 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |Indirizzo IP pubblico del servizio Edge Server A/V Edge  <br/> |Negoziazione STUN/TURN dei candidati su TCP sulla porta 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Indirizzo IP pubblico del servizio Edge Server A/V Edge  <br/> |Qualsiasi  <br/> |Negoziazione STUN/TURN dei candidati su TCP sulla porta 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tabella di riepilogo del firewall delle porte interne

|**Protocollo**|**TCP o UDP**|**Porta**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Uno degli elementi seguenti che eseguono il servizio gateway XMPP:  <br/> • Front End Server  <br/> • Indirizzo VIP del pool Front End che esegue il servizio gateway XMPP  <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico XMPP in uscita dal servizio gateway XMPP in esecuzione nel Front End Server o nel pool Front End.  <br/><br/> **Nota:** I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per [ulteriori informazioni, vedere Migrating XMPP federation.](../../../SfBServer2019/migration/migrating-xmpp-federation.md) |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Qualsiasi:  <br/> • Front End Server che contiene l'archivio di gestione centrale  <br/> • Pool Front End che contiene l'archivio di gestione centrale  <br/> |Interfaccia interna del server perimetrale  <br/> |Replica delle modifiche dall'archivio di gestione centrale al server perimetrale.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Qualsiasi:  <br/> • Front End Server  <br/> • Ogni Front End Server nel pool Front End  <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico di Conferenze Web dal Front End Server o da ogni Front End Server (se si dispone di un pool Front End) all'interfaccia interna del server perimetrale.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi:  <br/> • Front End Server  <br/> • Ogni Front End Server nel pool Front End  <br/> |Interfaccia interna del server perimetrale  <br/> |Percorso preferito per il trasferimento di supporti A/V tra gli utenti interni ed esterni e il Survivable Branch Appliance o il Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi:  <br/> • Front End Server  <br/> • Ogni Front End Server nel pool  <br/> |Interfaccia interna del server perimetrale  <br/> |Percorso di fallback per il trasferimento di supporti A/V tra gli utenti interni ed esterni e il Survivable Branch Appliance o il Survivable Branch Server, se la comunicazione UDP non funziona. TCP viene quindi utilizzato per i trasferimenti di file e la condivisione desktop.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller del servizio di registrazione centralizzato tramite Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzata, comandi della riga di comando (ClsController.exe) o agente (ClsAgent.exe) e raccolta dei registri.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller del servizio di registrazione centralizzato tramite Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzata, comandi della riga di comando (ClsController.exe) o agente (ClsAgent.exe) e raccolta dei registri.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller del servizio di registrazione centralizzato tramite Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzata, comandi della riga di comando (ClsController.exe) o agente (ClsAgent.exe) e raccolta dei registri.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>Ip virtuali con interfaccia esterna

|**Ruolo o protocollo**|**TCP o UDP**|**Porta di destinazione o intervallo di porte**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Non supportato in Skype for Businesss Server 2019 |TCP  <br/> |5269  <br/> |Qualsiasi  <br/> |Servizio proxy XMPP (condivide un indirizzo IP con il servizio Access Edge)  <br/> |Il servizio proxy XMPP accetta il traffico dai contatti XMPP nelle federazioni XMPP definite.  <br/> |
|XMPP  <br/>Non supportato in Skype for Businesss Server 2019 |TCP  <br/> |5269  <br/> |Servizio proxy XMPP (condivide un indirizzo IP con il servizio Access Edge)  <br/> |Qualsiasi  <br/> |Il servizio proxy XMPP invia il traffico dai contatti XMPP nelle federazioni XMPP definite.  <br/> |
|Access/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio Edge server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge server perimetrale <br/> |Traffico SIP da client a server per l'accesso degli utenti esterni.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio Edge server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge server perimetrale <br/> |Per la connettività di messaggistica istantanea pubblica e federata tramite SIP.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privato tramite NAT:** Servizio Edge server perimetrale <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge server perimetrale <br/> |Qualsiasi  <br/> |Per la connettività di messaggistica istantanea pubblica e federata tramite SIP.  <br/> |
|Web Conferencing/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio Edge Server Web Conferencing Edge <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Web Conferencing Edge del server perimetrale <br/> |Contenuti multimediali per conferenze Web.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio Edge Server A/V Edge <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server A/V Edge <br/> |Negoziazione STUN/TURN dei candidati su UDP sulla porta 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Servizio Edge Server A/V Edge <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server A/V Edge <br/> |Negoziazione STUN/TURN dei candidati su TCP sulla porta 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>Ip virtuali dell'interfaccia interna

Le nostre indicazioni qui saranno leggermente diverse. In realtà, in una situazione di bilanciamento del carico di rete, è ora consigliabile eseguire il routing attraverso un VIP interno solo nelle circostanze seguenti:
  
- Se si utilizza la messaggistica unificata di Exchange 2007 o Exchange 2010.
    
- Se si dispone di client legacy che usano edge.
    
La tabella seguente fornisce indicazioni per tali scenari, ma in caso contrario, dovrebbe essere possibile dipendere dall'archivio di gestione centrale (CMS) per instradare il traffico al singolo server perimetrale di cui è a conoscenza (ciò richiede che cms sia sempre aggiornato sulle informazioni dei server perimetrali).
  
|**Protocollo**|**TCP o UDP**|**Porta**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualsiasi:  <br/> • Director  <br/> • Indirizzo VIP del pool di server Director  <br/> • Front End Server  <br/> • Indirizzo VIP del pool Front End  <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico SIP in uscita dal Director, dall'indirizzo VIP del pool di server Director, dal Front End Server o dall'indirizzo VIP del pool Front End all'interfaccia interna del server perimetrale.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interfaccia VIP interna del server perimetrale  <br/> |Qualsiasi:  <br/> • Director  <br/> • Indirizzo VIP del pool di server Director  <br/> • Front End Server  <br/> • Indirizzo VIP del pool Front End  <br/> |Traffico SIP in ingresso verso il Director, l'indirizzo VIP del pool di server Director, il Front End Server o l'indirizzo VIP del pool Front End dall'interfaccia interna del server perimetrale.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Qualsiasi:  <br/> • Indirizzo IP del Front End Server  <br/> • Indirizzo IP del pool Front End  <br/> • Qualsiasi Survivable Branch Appliance che utilizza questo server perimetrale  <br/> • Qualsiasi Survivable Branch Server che utilizza questo server perimetrale  <br/> |Interfaccia interna del server perimetrale  <br/> |Autenticazione degli utenti A/V dal Front End Server o dal pool Front End oppure dal Survivable Branch Appliance o dal Survivable Branch Server utilizzando il server perimetrale.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Percorso preferito per il trasferimento di supporti A/V tra gli utenti interni ed esterni.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |Interfaccia VIP interna del server perimetrale  <br/> |Percorso di fallback per il trasferimento di supporti A/V tra gli utenti interni ed esterni se la comunicazione UDP non funziona. TCP viene quindi utilizzato per i trasferimenti di file e la condivisione desktop.  <br/> |
