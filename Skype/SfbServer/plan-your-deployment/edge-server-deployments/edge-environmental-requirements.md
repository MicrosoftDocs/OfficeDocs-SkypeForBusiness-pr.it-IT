---
title: Requisiti ambientali di Edge Server in Skype for Business Server
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
ms.openlocfilehash: 15cc6c54d420cd95962afb1faa219a3a370056a6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803376"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Requisiti ambientali di Edge Server in Skype for Business Server
 
**Riepilogo:** Informazioni sui requisiti ambientali per Edge Server in Skype for Business Server.
  
Una grande quantità di pianificazione e preparazione deve avvenire all'esterno dell'ambiente di Skype for Business Server Edge Server. In questo articolo rivediamo i preparativi da apportare nell'ambiente aziendale, come indicato nell'elenco seguente:
  
- [Pianificazione della topologia](edge-environmental-requirements.md#TopoPlan)
    
- [Pianificazione DNS](edge-environmental-requirements.md#DNSPlan)
    
- [Pianificazione del certificato](edge-environmental-requirements.md#CertPlan)
    
- [Pianificazione della porta e del firewall](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Pianificazione della topologia
<a name="TopoPlan"> </a>

Le topologie di Skype for Business Server Edge Server sono in grado di usare:
  
- Indirizzi IP pubblici instradabili.
    
- Indirizzi IP privati non instradabili, se viene usato NAT ( **Symmetric** Network Address Translation).
    
> [!TIP]
> Il server perimetrale può essere configurato per l'uso di un singolo indirizzo IP con porte distinte per ogni servizio oppure può usare indirizzi IP distinti per ogni servizio, ma usare la stessa porta predefinita (che per impostazione predefinita sarà TCP 443). Di seguito sono riportate altre informazioni nella sezione requisiti indirizzo IP. 
  
Se si scelgono indirizzi IP privati non instradabili con NAT, ricordare questi punti:
  
- È necessario usare indirizzi IP privati instradabili su **tutte e tre le** interfacce esterne.
    
- È necessario configurare il NAT **simmetrico** per il traffico in entrata e in uscita. La NAT simmetrica è l'unica NAT supportata che puoi usare con Skype for Business Server Edge Server.
    
- Configurare il NAT per non modificare gli indirizzi di origine in arrivo. Il servizio a/V Edge deve essere in grado di ricevere l'indirizzo di origine in entrata per trovare il percorso multimediale ottimale.
    
- Gli Edge Server devono essere in grado di comunicare tra loro dagli indirizzi IP pubblici A/V Edge. Il firewall deve consentire il traffico.
    
- NAT può essere usato **solo** per i server Edge consolidati in scala se si usa il bilanciamento del carico DNS. Se si usa il bilanciamento del carico hardware (HLB), è necessario usare gli indirizzi IP instradabili pubblicamente **senza** NAT.
    
Non ci sono problemi con le interfacce di Access, Web Conferencing e A/V Edge dietro un router o un firewall che esegue un NAT simmetrico per le topologie del server perimetrale consolidato singole e in scala (purché non si stia usando il bilanciamento del carico hardware).
  
### <a name="summary-of-edge-server-topology-options"></a>Riepilogo delle opzioni della topologia di Edge Server

Sono disponibili diverse opzioni di topologia per le distribuzioni di Skype for Business Server Edge Server:
  
- Singolo bordo consolidato con indirizzi IP privati e NAT
    
- Singolo bordo consolidato con indirizzi IP pubblici
    
- Edge consolidato in scala con indirizzi IP privati e NAT
    
- Edge consolidato in scala con indirizzi IP pubblici
    
- Edge consolidato in scala con i dispositivi di bilanciamento del carico hardware
    
Per aiutarti a sceglierne uno, la tabella seguente contiene un riepilogo delle opzioni disponibili per ogni topologia:
  
|**Topologia**|**Disponibilità elevata**|**Altri record DNS necessari per il server perimetrale esterno nel pool di bordi?**|**Failover Edge per le sessioni di Skype for Business Server**|**Failover Edge per le sessioni federative di Skype for Business Server**|
|:-----|:-----|:-----|:-----|:-----|
|Singolo bordo consolidato con indirizzi IP privati e NAT  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Singolo bordo consolidato con indirizzi IP pubblici  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Edge consolidato in scala con indirizzi IP privati e NAT (bilanciamento del carico DNS)  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì&sup1;  <br/> |
|Edge consolidato in scala con indirizzi IP pubblici (bilanciamento del carico DNS)  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì&sup1;  <br/> |
|Edge consolidato in scala con i dispositivi di bilanciamento del carico hardware  <br/> |Sì  <br/> |No (un record DNS per ogni VIP)  <br/> |Sì  <br/> |Sì  <br/> |
   
&sup1; Exchange Remote failover degli utenti remoti tramite il bilanciamento del carico DNS richiede Exchange 2013 o versioni successive.
  
### <a name="ip-address-requirements"></a>Requisiti per l'indirizzo IP

A livello fondamentale, tre servizi richiedono indirizzi IP; Access Edge Services, Web Conferencing Edge Services e A/V Edge Services. Si ha la possibilità di usare tre indirizzi IP, uno per ognuno dei servizi, oppure si può usare uno e scegliere di inserire ogni servizio in una porta diversa (è possibile controllare la sezione pianificazione della [porta e del firewall](edge-environmental-requirements.md#PortFirewallPlan) per altre informazioni su alcuni di questi). Per un singolo ambiente di Edge consolidato, è più o meno così.
  
> [!NOTE]
> Come indicato in precedenza, è possibile scegliere di avere un indirizzo IP per tutti e tre i servizi ed eseguirli in porte diverse. Ma per essere chiari, non è consigliabile. Se i clienti non riescono ad accedere alle porte alternative da usare in questo scenario, non possono accedere alla funzionalità completa dell'ambiente Edge. 
  
Può essere un po' più complicato con le topologie consolidate in scala, quindi esaminiamo alcune tabelle che stabiliscono i requisiti per l'indirizzo IP, tenendo presente che i punti di decisione principali per la selezione della topologia sono l'elevata disponibilità e il bilanciamento del carico. Le esigenze di elevata disponibilità possono influenzare la scelta di bilanciamento del carico (ne parleremo di più dopo le tabelle).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisiti per l'indirizzo IP per il bordo consolidato in scala (indirizzo IP per ruolo)

|**Numero di server perimetrali per pool**|**Numero di indirizzi IP necessari per il bilanciamento del carico DNS**|**Numero di indirizzi IP necessari per il bilanciamento del carico hardware**|
|:-----|:-----|:-----|
|2  <br/> |6  <br/> |3 (1 per VIP) + 6  <br/> |
|3  <br/> |9  <br/> |3 (1 per VIP) + 9  <br/> |
|4  <br/> |12  <br/> |3 (1 per VIP) + 12  <br/> |
|5  <br/> |15  <br/> |3 (1 per VIP) + 15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Requisiti per l'indirizzo IP per il bordo consolidato in scala (singolo indirizzo IP per tutti i ruoli)

|**Numero di server perimetrali per pool**|**Numero di indirizzi IP necessari per il bilanciamento del carico DNS**|**Numero di indirizzi IP necessari per il bilanciamento del carico hardware**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1 (1 per VIP) + 2  <br/> |
|3  <br/> |3  <br/> |1 (1 per VIP) + 3  <br/> |
|4  <br/> |4  <br/> |1 (1 per VIP) + 4  <br/> |
|5  <br/> |5  <br/> |1 (1 per VIP) + 5  <br/> |
   
Esaminiamo alcuni altri aspetti da considerare durante la pianificazione.
  
- **Disponibilità elevata**: se è necessaria una disponibilità elevata nella distribuzione, è consigliabile distribuire almeno due server perimetrali in un pool. È importante notare che un singolo pool di Edge supporta fino a 12 Edge Server (anche se Generatore di topologie consente di aggiungere fino a 20, non testato o supportato, quindi ti consigliamo di non farlo). Se hai bisogno di più di 12 Edge Server, devi creare altri pool di bordi.
    
- **Bilanciamento del carico hardware**: è consigliabile il bilanciamento del carico DNS per la maggior parte degli scenari. Il bilanciamento del carico hardware è anche supportato, naturalmente, ma in particolare è necessario per un singolo scenario sul bilanciamento del carico DNS:
    
  - Accesso esterno alla messaggistica unificata di Exchange 2007 o Exchange 2010 (senza SP).
    
- **Bilanciamento del carico DNS**: per la messaggistica unificata, Exchange 2010 SP1 e versioni successive possono essere supportate dal bilanciamento del carico DNS. Tieni presente che se hai bisogno di usare il bilanciamento del carico DNS per una versione precedente di Exchange, il lavoro verrà eseguito, ma tutto il traffico per questa operazione passerà al primo server nel pool e, se non è disponibile, il traffico fallirà in seguito.
    
    Il bilanciamento del carico DNS è consigliato anche se si sta eseguendo la Federazione con aziende che usano:
- Skype for Business Server 2015:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft Office Office 365
- Skype for Business Server 2019:
    - Lync Server 2013
    - Skype for Business Server 2015
    - Microsoft Office 365.
    
## <a name="dns-planning"></a>Pianificazione DNS
<a name="DNSPlan"> </a>

Per quanto riguarda la distribuzione di Skype for Business Server Edge Server, è essenziale preparare correttamente il DNS. Con i record giusti in posizione, la distribuzione sarà molto più semplice. Si spera di aver scelto una topologia nella sezione precedente, mentre si sta per eseguire una panoramica e quindi elencare un paio di tabelle che delineano i record DNS per tali scenari. Per una lettura più approfondita, se necessario, avremo anche una [pianificazione DNS avanzata di Edge Server per Skype for Business Server](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) .
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>Record DNS per scenari singoli server perimetrali consolidati

Questi saranno i record DNS che ti serviranno per un server Edge singe usando IP pubblici o IPs privati con NAT. Dato che si tratta di dati di esempio, daremo un esempio di IPs in modo da poter elaborare le proprie voci più facilmente:
  
- Scheda di rete interna: 172.25.33.10 (nessun gateway predefinito assegnato)
    
    > [!NOTE]
    > Verificare che ci sia una route dalla rete che contiene l'interfaccia interna di Edge a tutte le reti che contengono server che utilizzano i client di Skype for Business Server o Lync Server 2013, ad esempio da 172.25.33.0 a 192.168.10.0. 
  
- Scheda di rete esterna:
    
  - Indirizzi IP pubblici:
    
  - Access Edge: 131.107.155.10 (questo è il principale, con il gateway predefinito impostato sul router pubblico, es: 131.107.155.1)
    
  - Web Conferencing Edge: 131.107.155.20 (secondario)
    
  - A/V Edge: 131.107.155.30 (secondario)
    
  Gli indirizzi IP pubblici di Web Conferencing e A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà di Internet Protocol versione 4 (TCP/IPv4) e protocollo Internet versione 6 (TCP/IPv6) delle proprietà di connessione dell'area locale in Windows Server.
    
  - IPs privato:
    
  - Access Edge: 10.45.16.10 (questo è il principale, con il gateway predefinito impostato sul router, es: 10.45.16.1)
    
  - Web Conferencing Edge: 10.45.16.20 (secondario)
    
  - A/V Edge: 10.45.16.30 (secondario)
    
Gli indirizzi IP pubblici di Web Conferencing e A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà di Internet Protocol versione 4 (TCP/IPv4) e protocollo Internet versione 6 (TCP/IPv6) delle proprietà di connessione dell'area locale in Windows Server.
  
> [!TIP]
>Ecco altre possibili configurazioni:
  
- È possibile usare un indirizzo IP sulla scheda di rete esterna. Questa operazione non è consigliabile perché è necessario distinguere i servizi di thee con porte diverse (che è possibile eseguire in Skype for Business Server), ma esistono alcuni firewall che potrebbero bloccare le porte alternative. Per altre informazioni, vedere la sezione [pianificazione della porta e del firewall](edge-environmental-requirements.md#PortFirewallPlan) .
    
- È possibile avere tre schede di rete esterne anziché una e assegnare uno degli IP del servizio a ognuno. Perché eseguire questa operazione? Separerebbe i servizi e se qualcosa andasse storto, ciò renderebbe più facile la risoluzione dei problemi e lascerebbe che gli altri servizi continuino a funzionare mentre si risolve un problema.
    
|**Posizione**|**Tipo**|**Porta**|**Record FQDN o DNS**|**Indirizzo IP o FQDN**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS esterno  <br/> |Un record  <br/> |NA  <br/> |sip.contoso.com  <br/> |**pubblico:** 131.107.155.10 <br/> **privato:** 10.45.16.10 <br/> |Interfaccia esterna per il servizio Edge di Access. Sarà necessario uno per ogni dominio SIP con gli utenti di Skype for business.  <br/> |
|DNS esterno  <br/> |Un record  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**pubblico:** 131.107.155.20 <br/> **privato:** 10.45.16.20 <br/> |Interfaccia esterna per il servizio Web Conferencing Edge.  <br/> |
|DNS esterno  <br/> |Un record  <br/> |NA  <br/> |av.contoso.com  <br/> |**pubblico:** 131.107.155.30 <br/> **privato:** 10.45.16.30 <br/> |Interfaccia esterna per il servizio A/V Edge.  <br/> |
|DNS esterno  <br/> |Record SRV  <br/> |443  <br/> |_sip. _tls. contoso. com  <br/> |sip.contoso.com  <br/> |Interfaccia esterna per il servizio Edge di Access. Questo record SRV è necessario per i client Skype for Business Server, Lync Server 2013 e Lync Server 2010 per l'utilizzo esterno. Sarà necessario uno per ogni dominio con gli utenti di Skype for business.  <br/> |
|DNS esterno  <br/> |Record SRV  <br/> |5061  <br/> |_sipfederationtls. _tcp. contoso. com  <br/> |sip.contoso.com  <br/> |Interfaccia esterna per il servizio Edge di Access. Questo record SRV è necessario per l'individuazione automatica di DNS dei partner federati denominati domini SIP consentiti. Sarà necessario uno per ogni dominio con gli utenti di Skype for business.  <br/> |
|DNS interno  <br/> |Un record  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |Interfaccia interna per il bordo consolidato.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>Record DNS per scenari DNS scalati e hardware Edge Server

Questi saranno i record DNS che ti serviranno per un server Edge singe usando IP pubblici o IPs privati con NAT. Dato che si tratta di dati di esempio, daremo un esempio di IPs in modo da poter elaborare le proprie voci più facilmente:
  
- Scheda di rete interna:
    
  - Nodo 1:172.25.33.10 (nessun gateway predefinito assegnato)
    
  - Nodo 2:172.25.33.11 (nessun gateway predefinito assegnato)
    
    > [!NOTE]
    > Verificare che ci sia una route dalla rete che contiene l'interfaccia interna di Edge a tutte le reti che contengono server che utilizzano i client di Skype for Business Server o Lync Server 2013, ad esempio da 172.25.33.0 a 192.168.10.0. 
  
- Scheda di rete esterna:
    
  - Nodo 1
    
     - Indirizzi IP pubblici:
    
        - Access Edge: 131.107.155.10 (questo è il principale, con il gateway predefinito impostato sul router pubblico, es: 131.107.155.1)
    
        - Web Conferencing Edge: 131.107.155.20 (secondario)
    
        - A/V Edge: 131.107.155.30 (secondario)
    
          Gli indirizzi IP pubblici di Web Conferencing e A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà di Internet Protocol versione 4 (TCP/IPv4) e protocollo Internet versione 6 (TCP/IPv6) delle proprietà di connessione dell'area locale in Windows Server.
    
    - IPs privato:
    
         - Access Edge: 10.45.16.10 (questo è il principale, con il gateway predefinito impostato sul router, es: 10.45.16.1)
    
         - Web Conferencing Edge: 10.45.16.20 (secondario)
    
         - A/V Edge: 10.45.16.30 (secondario)
    
      Gli indirizzi IP pubblici di Web Conferencing e A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà di Internet Protocol versione 4 (TCP/IPv4) e protocollo Internet versione 6 (TCP/IPv6) delle proprietà di connessione dell'area locale in Windows Server.
    
  - Nodo 2
    
    - Indirizzi IP pubblici:
    
      - Access Edge: 131.107.155.11 (questo è il principale, con il gateway predefinito impostato sul router pubblico, es: 131.107.155.1)
    
      - Web Conferencing Edge: 131.107.155.21 (secondario)
    
      - A/V Edge: 131.107.155.31 (secondario)
    
      Gli indirizzi IP pubblici di Web Conferencing e A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà di Internet Protocol versione 4 (TCP/IPv4) e protocollo Internet versione 6 (TCP/IPv6) delle proprietà di connessione dell'area locale in Windows Server.
    
  - IPs privato:
    
    - Access Edge: 10.45.16.11 (questo è il principale, con il gateway predefinito impostato sul router, es: 10.45.16.1)
    
    - Web Conferencing Edge: 10.45.16.21 (secondario)
    
    - A/V Edge: 10.45.16.31 (secondario)
    
      Gli indirizzi IP pubblici di Web Conferencing e A/V Edge sono indirizzi IP aggiuntivi (secondari) nella sezione Advanced delle proprietà di Internet Protocol versione 4 (TCP/IPv4) e protocollo Internet versione 6 (TCP/IPv6) delle proprietà di connessione dell'area locale in Windows Server.
    
Ecco altre possibili configurazioni:
  
- È possibile usare un indirizzo IP sulla scheda di rete esterna. Questa operazione non è consigliabile perché è necessario distinguere i servizi di thee con porte diverse (che è possibile eseguire in Skype for Business Server), ma esistono alcuni firewall che potrebbero bloccare le porte alternative. Per altre informazioni, vedere la sezione [pianificazione della porta e del firewall](edge-environmental-requirements.md#PortFirewallPlan) .
    
- È possibile avere tre schede di rete esterne anziché una e assegnare uno degli IP del servizio a ognuno. Perché eseguire questa operazione? Separerebbe i servizi e se qualcosa andasse storto, ciò renderebbe più facile la risoluzione dei problemi e lascerebbe che gli altri servizi continuino a funzionare mentre si risolve un problema.
    
|**Posizione**|**Tipo**|**Porta**|**Record FQDN o DNS**|**Indirizzo IP o FQDN**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS esterno  <br/> |Un record  <br/> |NA  <br/> |sip.contoso.com  <br/> |**pubblico:** 131.107.155.10 e 131.107.155.11 <br/> **privato:** 10.45.16.10 e 10.45.16.11 <br/> |Interfaccia esterna per il servizio Edge di Access. Sarà necessario uno per ogni dominio SIP con gli utenti di Skype for business.  <br/> |
|DNS esterno  <br/> |Un record  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**pubblico:** 131.107.155.20 e 131.107.155.21 <br/> **privato:** 10.45.16.20 e 10.45.16.21 <br/> |Interfaccia esterna per il servizio Web Conferencing Edge.  <br/> |
|DNS esterno  <br/> |Un record  <br/> |NA  <br/> |av.contoso.com  <br/> |**pubblico:** 131.107.155.30 e 131.107.155.31 <br/> **privato:** 10.45.16.30 e 10.45.16.31 <br/> |Interfaccia esterna per il servizio A/V Edge.  <br/> |
|DNS esterno  <br/> |Record SRV  <br/> |443  <br/> |_sip. _tls. contoso. com  <br/> |sip.contoso.com  <br/> |Interfaccia esterna per il servizio Edge di Access. Questo record SRV è necessario per i client Skype for Business Server, Lync Server 2013 e Lync Server 2010 per l'utilizzo esterno. Sarà necessario uno per ogni dominio con Skype for business.  <br/> |
|DNS esterno  <br/> |Record SRV  <br/> |5061  <br/> |_sipfederationtls. _tcp. contoso. com  <br/> |sip.contoso.com  <br/> |Interfaccia esterna per il servizio Edge di Access. Questo record SRV è necessario per l'individuazione automatica di DNS dei partner federati denominati domini SIP consentiti. Sarà necessario uno per ogni dominio con Skype for business.  <br/> |
|DNS interno  <br/> |Un record  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 e 172.25.33.11  <br/> |Interfaccia interna per il bordo consolidato.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Record DNS per la Federazione (tutti gli scenari)

|**Posizione**|**Tipo**|**Porta**|**FQDN**|**Record host FQDN**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS esterno  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp. contoso. com  <br/> |sip.contoso.com  <br/> |Interfaccia esterna di Access Edge SIP necessaria per l'individuazione automatica del DNS. Usato dagli altri potenziali partner federativi. È anche noto come "Consenti domini SIP". Sarà necessario uno di questi per ogni dominio SIP con gli utenti di Skype for business.  <br/><br/> **Nota:** Sarà necessario questo record SRV per la mobilità e la camera di compensazione delle notifiche push. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Record DNS per il protocollo di messaggistica e presenza estensibile

|**Posizione**|**Tipo**|**Porta**|**FQDN**|**Indirizzo IP o record host FQDN**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS esterno  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server. _tcp. contoso. com  <br/> |xmpp.contoso.com  <br/> |Interfaccia proxy XMPP nel servizio Edge di Access o nel pool di Edge. È necessario ripetere questa operazione in base alle esigenze per tutti i domini SIP interni con gli utenti abilitati per Skype for Business Server, in cui è consentito il contatto con i contatti XMPP:  <br/> • un criterio globale  <br/> • un criterio sito in cui l'utente è abilitato  <br/> • un criterio utente applicato all'utente abilitato per Skype for Business Server  <br/> Anche i criteri XMPP consentiti devono essere configurati nel criterio utenti federati XMPP.  <br/> |
|DNS esterno  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |Indirizzo IP del servizio Access Edge nell'Edge Server o nel pool di Edge che ospita il servizio proxy XMPP  <br/> |Questa operazione punta al servizio Access Edge nell'Edge Server o al pool di Edge che ospita il servizio proxy XMPP. In genere il record SRV creato punterà al record host (A o AAAA).  <br/> |
   
> [!NOTE]
> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per altre informazioni, Vedi [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .

## <a name="certificate-planning"></a>Pianificazione del certificato
<a name="CertPlan"> </a>

Skype for Business Server usa i certificati per comunicazioni sicure e crittografate sia tra server che da server a client. Come previsto, i certificati dovranno avere i record DNS per i server in modo che corrispondano a qualsiasi nome soggetto (SN) e al nome alternativo soggetto (SAN) nei certificati. Ora, in fase di pianificazione, il lavoro sarà necessario per verificare di avere gli FQDN giusti registrati nel DNS per le voci SN e SAN per i certificati.
  
Verranno illustrate separatamente le esigenze dei certificati esterni e interni e quindi verrà visualizzata una tabella che fornisce i requisiti per entrambi.
  
### <a name="external-certificates"></a>Certificati esterni

Il certificato assegnato alle interfacce del server perimetrale esterno deve essere almeno disponibile da un'autorità di certificazione pubblica (CA). Non è possibile consigliare una CA specifica, ma è disponibile un elenco di CAs, i partner di certificati per le [comunicazioni unificate](/SkypeForBusiness/certification/services-ssl) a cui si può dare un'occhiata per vedere se è elencata la CA preferita.
  
Quando è necessario inviare una richiesta a una CA per il certificato pubblico e come si esegue questa operazione? Per eseguire questa operazione è necessario un paio di modi:
  
- È possibile passare all'installazione di Skype for Business Server e quindi alla distribuzione di Edge Server. La distribuzione guidata di Skype for Business Server avrà un passaggio per generare una richiesta di certificato, che potrà quindi essere inviata alla CA selezionata.
    
- Puoi anche usare i comandi di Windows PowerShell per generare questa richiesta, se è più in linea con le esigenze aziendali o la strategia di distribuzione.
    
- Infine, la CA può avere un processo di invio personalizzato, che può anche coinvolgere Windows PowerShell o un altro metodo. In questo caso, è necessario affidarsi alla propria documentazione, oltre alle informazioni fornite qui per il riferimento.
    
Dopo aver ottenuto il certificato, è necessario procedere e assegnarlo a questi servizi in Skype for Business Server:
  
- Interfaccia del servizio Access Edge
    
- Interfaccia del servizio Web Conferencing Edge
    
- Servizio di autenticazione audio/video (non confondere questo con l'A/V Edge service, perché non usa un certificato per crittografare i flussi audio e video)
    
> [!IMPORTANT]
> Tutti i server perimetrali, se appartenenti allo stesso pool di Edge Server, devono avere lo stesso certificato esatto con la stessa chiave privata per il servizio di autenticazione di inoltro multimediale. 
  
### <a name="internal-certificates"></a>Certificati interni

Per l'interfaccia Internal Edge Server, è possibile usare un certificato pubblico di una CA pubblica o un certificato emesso dalla CA interna dell'organizzazione. La cosa da ricordare sul certificato interno è che usa una voce SN e non ci sono voci di SAN, quindi non devi preoccuparti di SAN sul cert interno.
  
### <a name="required-certificates-table"></a>Tabella certificati obbligatori

Qui c'è un tavolo per aiutarti con le tue richieste. Le voci FQDN sono solo per i domini di esempio. Dovrai effettuare richieste in base a domini privati e pubblici, ma ecco una guida a ciò che abbiamo usato:
  
- Contoso<span></span>. com: FQDN pubblico
    
- Fabrikam<span></span>. com: Second FQDN pubblico (aggiunta come demo di cosa richiedere se si hanno più domini SIP)
    
- Contoso<span></span>.NET: dominio interno
    
#### <a name="edge-certificate-table"></a>Tabella certificati Edge

Indipendentemente dal fatto che si stia eseguendo un singolo Edge Server o un pool di Edge, è necessario per il certificato:
  
|**Componente**|**Nome soggetto (SN)**|**Nomi alternativi oggetto (SAN)/Order**|**Note**|
|:-----|:-----|:-----|:-----|
|Bordo esterno  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Questo è il certificato necessario per richiedere da una CA pubblica. Dovrà essere assegnata alle interfacce Edge esterne per gli elementi seguenti:  <br/> • Access Edge  <br/> • Web Conferencing Edge  <br/> • Autenticazione audio/video  <br/> <br/>La buona notizia è che i SANs vengono aggiunti automaticamente alla richiesta di certificato e quindi il certificato dopo l'invio della richiesta, in base alle informazioni definite per la distribuzione in Generatore di topologie. È necessario aggiungere solo le voci SAN per eventuali altri domini SIP o altre voci che è necessario supportare. Perché sip.contoso.com è replicato in questa istanza? Anche questo avviene automaticamente ed è necessario che le cose funzionino correttamente.  <br/><br/> **Nota:** Questo certificato può essere usato anche per la connettività di messaggistica istantanea pubblica. Non è necessario eseguire alcuna operazione in modo diverso, ma nelle versioni precedenti di questa documentazione è stato elencato come tabella separata e ora non lo è. <br/> |
|Bordo interno  <br/> |sfbedge.contoso.com  <br/> |NA  <br/> |Puoi ottenere questo certificato da una CA pubblica o da una CA interna. Sarà necessario contenere l'EKU del server (utilizzo della chiave avanzata) e assegnarlo all'interfaccia bordo interno.  <br/> |
   
Se è necessario un certificato per il protocollo XMPP (Extensible Messaging and Presence Protocol), l'aspetto sarà identico alle voci della tabella perimetrale esterna, ma avrà le due voci di SAN aggiuntive seguenti:
  
- XMPP. <span> </span>Contoso<span></span>. com
    
- \*. contoso<span></span>. com
    
Tieni presente che attualmente XMPP è supportato solo in Skype for Business Server per Google Talk, se vuoi o hai bisogno di usarlo per qualsiasi altra cosa, devi confermare questa funzionalità con il fornitore di terze parti coinvolto.
  
## <a name="port-and-firewall-planning"></a>Pianificazione della porta e del firewall
<a name="PortFirewallPlan"> </a>

Ottenere la pianificazione corretta per le porte e i firewall per le distribuzioni di Skype for Business Server Edge Server è possibile salvare giorni o settimane di risoluzione dei problemi e stress. Di conseguenza, elenchiamo un paio di tabelle che indicheranno l'utilizzo del protocollo e le porte che è necessario aprire, in ingresso e in uscita, sia per gli scenari NAT che per quelli IP pubblici. Avremo anche tabelle separate per gli scenari di bilanciamento del carico hardware (HLB) e altre indicazioni. Per altre informazioni, abbiamo anche alcuni [scenari di Edge Server in Skype for Business Server](scenarios.md) che puoi verificare per i tuoi particolari problemi di distribuzione.
  
### <a name="general-protocol-usage"></a>Utilizzo di protocollo generale

Prima di esaminare le tabelle di riepilogo per i firewall esterni e interni, consideriamo anche la tabella seguente:
  
|**Trasporto audio/video**|**L'uso**|
|:-----|:-----|
|UDP  <br/> |Il protocollo di livello di trasporto preferito per audio e video.  <br/> |
|TCP  <br/> |Protocollo di livello di trasporto di fallback per audio e video.  <br/> Il protocollo di livello di trasporto richiesto per la condivisione delle applicazioni in Skype for Business Server, Lync Server 2013 e Lync Server 2010.  <br/> Il protocollo del livello di trasporto richiesto per il trasferimento di file in Skype for Business Server, Lync Server 2013 e Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tabella di riepilogo del firewall della porta esterna

L'indirizzo IP di origine e quello di destinazione conterranno informazioni per gli utenti che usano indirizzi IP privati con NAT, oltre a persone che usano indirizzi IP pubblici. In questo modo verranno illustrate tutte le permutazioni degli [scenari di Edge Server nella sezione Skype for Business Server](scenarios.md) .
  
|**Ruolo o protocollo**|**TCP o UDP**|**Porta di destinazione o intervallo di porte**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Non supportato in Skype for Business Server 2019 |TCP  <br/> |5269  <br/> |Qualsiasi  <br/> |Servizio proxy XMPP (condivide un indirizzo IP con il servizio Access Edge  <br/> |Il servizio proxy XMPP accetta il traffico da contatti XMPP in federazioni XMPP definite.  <br/> |
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |**IP privato tramite NAT:** Edge Server Access Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server perimetrale <br/> |Qualsiasi  <br/> |Revoca di certificati e verifica e recupero CRL.  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |**IP privato tramite NAT:** Edge Server Access Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server perimetrale <br/> |Qualsiasi  <br/> |Query DNS su TCP.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |**IP privato tramite NAT:** Edge Server Access Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server perimetrale <br/> |Qualsiasi  <br/> |Query DNS su UDP.  <br/> |
|Access/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Edge Server Access Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server perimetrale <br/> |Traffico SIP da client a server per l'accesso degli utenti esterni.  <br/> |
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Edge Server Access Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server perimetrale <br/> |Per la connettività di messaggistica istantanea federata e pubblica con SIP.  <br/> |
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privato tramite NAT:** Edge Server Access Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server perimetrale <br/> |Qualsiasi  <br/> |Per la connettività di messaggistica istantanea federata e pubblica con SIP.  <br/> |
|Web Conferencing/PSOM (TLS)  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Edge Server Web Conferencing Edge service <br/> **IP pubblico:** Indirizzo IP pubblico di Edge Server Web Conferencing Edge <br/> |Elementi multimediali Web Conferencing.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**IP privato tramite NAT:** Edge Server A/V Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge A/V Edge Server <br/> |Qualsiasi  <br/> |Viene usato per l'inoltro del traffico multimediale.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**IP privato tramite NAT:** Edge Server A/V Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge A/V Edge Server <br/> |Qualsiasi  <br/> |Viene usato per l'inoltro del traffico multimediale.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**IP privato tramite NAT:** Edge Server A/V Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge A/V Edge Server <br/> |Qualsiasi  <br/> |3478 in uscita è:  <br/> • Usato da Skype for Business Server per determinare la versione di Edge Server con cui sta comunicando.  <br/> • Usato per il traffico multimediale tra Edge Server.  <br/> • Obbligatorio per la Federazione con Lync Server 2010.  <br/> • Necessario se sono distribuiti più pool di Edge all'interno dell'organizzazione.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Edge Server A/V Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge A/V Edge Server <br/> |Negoziazione per STORDIre/trasformare i candidati su UDP sulla porta 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Edge Server A/V Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge A/V Edge Server <br/> |Negoziazione STORDIre/trasformare i candidati su TCP sulla porta 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**IP privato tramite NAT:** Edge Server A/V Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge A/V Edge Server <br/> |Qualsiasi  <br/> |Negoziazione STORDIre/trasformare i candidati su TCP sulla porta 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tabella di riepilogo firewall porte interne

|**Protocollo**|**TCP o UDP**|**Porta**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Uno dei seguenti servizi gateway XMPP:  <br/> • Server front-end  <br/> • Pool Front-End  <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico XMPP in uscita dal servizio gateway XMPP in uso nel server front-end o nel pool Front-end.  <br/> **Nota:** I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per altre informazioni, Vedi [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Qualsiasi  <br/> • Director  <br/> • Pool di Director  <br/> • Server front-end  <br/> • Pool Front-End  <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico SIP in uscita da Director, pool di Director, server front-end o pool Front-end all'interfaccia interna del server perimetrale.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interfaccia interna del server perimetrale  <br/> |Qualsiasi  <br/> • Director  <br/> • Pool di Director  <br/> • Server front-end  <br/> • Pool Front-End  <br/> |Traffico SIP in ingresso per il Director, il pool di Director, il front end server o il pool Front end dall'interfaccia interna del server perimetrale.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Qualsiasi  <br/> • Server front-end  <br/> • Ogni server front-end  <br/>  nel pool Front-End <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico di Web Conferencing dal server front-end o da ogni server front-end (se si ha un pool Front-End) all'interfaccia interna del server perimetrale.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Qualsiasi  <br/> • Server front-end  <br/> • Pool Front-End  <br/> • Qualsiasi Appliance Survivable Branch che usa questo Edge Server  <br/> • Qualsiasi Survivable Branch Server che usa questo Edge Server  <br/> |Interfaccia interna del server perimetrale  <br/> |Autenticazione degli utenti A/V dal server front-end o dal pool Front-end o dal Survivable Branch Appliance o Survivable Branch Server, usando il server perimetrale.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni e il Survivable Branch Appliance o Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni e il Survivable Branch Appliance o Survivable Branch Server, se la comunicazione UDP non funziona. TCP viene quindi usato per i trasferimenti di file e la condivisione desktop.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Qualsiasi  <br/> • Front End Server che contiene l'Central Management store  <br/> • Pool Front end che contiene l'Central Management store  <br/> |Interfaccia interna del server perimetrale  <br/> |Replica delle modifiche apportate dall'archivio di gestione centrale al server perimetrale.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller di servizio di registrazione centralizzato con Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzato, ClsController Command line (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller di servizio di registrazione centralizzato con Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzato, ClsController Command line (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller di servizio di registrazione centralizzato con Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzato, ClsController Command line (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Dispositivi di bilanciamento del carico hardware per le tabelle porta Edge

Stiamo dando agli hardware di bilanciamento del carico (HLBs) e alle porte Edge la propria sezione, in quanto le cose sono un po' più complicate con l'hardware aggiuntivo. Vedere le tabelle seguenti per indicazioni su questo particolare scenario:
  
#### <a name="external-port-firewall-summary-table"></a>Tabella di riepilogo del firewall della porta esterna

L'indirizzo IP di origine e quello di destinazione conterranno informazioni per gli utenti che usano indirizzi IP privati con NAT, oltre a persone che usano indirizzi IP pubblici. In questo modo verranno illustrate tutte le permutazioni degli [scenari di Edge Server nella sezione Skype for Business Server](scenarios.md) .
  
|**Ruolo o protocollo**|**TCP o UDP**|**Porta di destinazione o intervallo di porte**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |Indirizzo IP pubblico del servizio Edge Server perimetrale  <br/> |Qualsiasi  <br/> |Revoca di certificati e verifica e recupero CRL.  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |Indirizzo IP pubblico del servizio Edge Server perimetrale  <br/> |Qualsiasi  <br/> |Query DNS su TCP.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |Indirizzo IP pubblico del servizio Edge Server perimetrale  <br/> |Qualsiasi  <br/> |Query DNS su UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Indirizzo IP del servizio Edge A/V Edge Server  <br/> |Qualsiasi  <br/> |Viene usato per l'inoltro del traffico multimediale.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Indirizzo IP pubblico del servizio Edge A/V Edge Server  <br/> |Qualsiasi  <br/> |Viene usato per l'inoltro del traffico multimediale.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Indirizzo IP pubblico del servizio Edge A/V Edge Server  <br/> |Qualsiasi  <br/> |3478 in uscita è:  <br/> • Usato da Skype for Business Server per determinare la versione di Edge Server con cui sta comunicando.  <br/> • Usato per il traffico multimediale tra Edge Server.  <br/> • Obbligatorio per la Federazione.  <br/> • Necessario se sono distribuiti più pool di Edge all'interno dell'organizzazione.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> |Indirizzo IP pubblico del servizio Edge A/V Edge Server  <br/> |Negoziazione per STORDIre/trasformare i candidati su UDP sulla porta 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |Indirizzo IP pubblico del servizio Edge A/V Edge Server  <br/> |Negoziazione STORDIre/trasformare i candidati su TCP sulla porta 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Indirizzo IP pubblico del servizio Edge A/V Edge Server  <br/> |Qualsiasi  <br/> |Negoziazione STORDIre/trasformare i candidati su TCP sulla porta 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tabella di riepilogo firewall porte interne

|**Protocollo**|**TCP o UDP**|**Porta**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Uno dei seguenti servizi gateway XMPP:  <br/> • Server front-end  <br/> • Indirizzo VIP del pool Front-end che gestisce il servizio gateway XMPP  <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico XMPP in uscita dal servizio gateway XMPP in uso nel server front-end o nel pool Front-end.  <br/><br/> **Nota:** I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per altre informazioni, Vedi [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Qualsiasi  <br/> • Front End Server che contiene l'Central Management store  <br/> • Pool Front end che contiene l'Central Management store  <br/> |Interfaccia interna del server perimetrale  <br/> |Replica delle modifiche apportate dall'archivio di gestione centrale al server perimetrale.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Qualsiasi  <br/> • Server front-end  <br/> • Ogni server front-end nel pool Front-End  <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico di Web Conferencing dal server front-end o da ogni server front-end (se si ha un pool Front-End) all'interfaccia interna del server perimetrale.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> • Server front-end  <br/> • Ogni server front-end nel pool Front-End  <br/> |Interfaccia interna del server perimetrale  <br/> |Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni e il Survivable Branch Appliance o Survivable Branch Server.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> • Server front-end  <br/> • Ogni server front-end nel pool  <br/> |Interfaccia interna del server perimetrale  <br/> |Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni e il Survivable Branch Appliance o Survivable Branch Server, se la comunicazione UDP non funziona. TCP viene quindi usato per i trasferimenti di file e la condivisione desktop.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller di servizio di registrazione centralizzato con Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzato, ClsController Command line (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller di servizio di registrazione centralizzato con Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzato, ClsController Command line (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Controller di servizio di registrazione centralizzato con Skype for Business Server Management Shell e cmdlet del servizio di registrazione centralizzato, ClsController Command line (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>IPs virtuale di interfaccia esterna

|**Ruolo o protocollo**|**TCP o UDP**|**Porta di destinazione o intervallo di porte**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Non supportato in Skype for Businesss server 2019 |TCP  <br/> |5269  <br/> |Qualsiasi  <br/> |Servizio proxy XMPP (condivide un indirizzo IP con il servizio Access Edge)  <br/> |Il servizio proxy XMPP accetta il traffico da contatti XMPP in federazioni XMPP definite.  <br/> |
|XMPP  <br/>Non supportato in Skype for Businesss server 2019 |TCP  <br/> |5269  <br/> |Servizio proxy XMPP (condivide un indirizzo IP con il servizio Access Edge)  <br/> |Qualsiasi  <br/> |Il servizio proxy XMPP invia il traffico da contatti XMPP in federazioni XMPP definite.  <br/> |
|Access/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Edge Server Access Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server perimetrale <br/> |Traffico SIP da client a server per l'accesso degli utenti esterni.  <br/> |
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Edge Server Access Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server perimetrale <br/> |Per la connettività di messaggistica istantanea federata e pubblica con SIP.  <br/> |
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privato tramite NAT:** Edge Server Access Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge Server perimetrale <br/> |Qualsiasi  <br/> |Per la connettività di messaggistica istantanea federata e pubblica con SIP.  <br/> |
|Web Conferencing/PSOM (TLS)  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Edge Server Web Conferencing Edge service <br/> **IP pubblico:** Indirizzo IP pubblico di Edge Server Web Conferencing Edge <br/> |Elementi multimediali Web Conferencing.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Edge Server A/V Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge A/V Edge Server <br/> |Negoziazione per STORDIre/trasformare i candidati su UDP sulla porta 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |**IP privato tramite NAT:** Edge Server A/V Edge service <br/> **IP pubblico:** Indirizzo IP pubblico del servizio Edge A/V Edge Server <br/> |Negoziazione STORDIre/trasformare i candidati su TCP sulla porta 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>Indirizzi IP virtuali di interfacce interne

Le nostre indicazioni saranno un po' diverse. In realtà, in una situazione di HLB, ora consigliamo di avere solo il routing attraverso un VIP interno nelle circostanze seguenti:
  
- Se si usa la messaggistica unificata di Exchange 2007 o Exchange 2010.
    
- Se si hanno client legacy che usano il bordo.
    
La tabella seguente fornisce indicazioni per questi scenari, ma in caso contrario dovrebbe essere in grado di dipendere da Central Management store (CMS) per instradare il traffico verso il singolo Edge Server a cui è a conoscenza (questo richiede che il CMS sia mantenuto aggiornato nel server perimetrale informazioni, naturalmente).
  
|**Protocollo**|**TCP o UDP**|**Porta**|**Indirizzo IP di origine**|**Indirizzo IP di destinazione**|**Note**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualsiasi  <br/> • Director  <br/> • Indirizzo VIP del pool di Director  <br/> • Server front-end  <br/> • Indirizzo VIP del pool Front-End  <br/> |Interfaccia interna del server perimetrale  <br/> |Traffico SIP in uscita da Director, indirizzo VIP del pool di Director, server front-end o indirizzo VIP del pool Front-end all'interfaccia interna del server perimetrale.  <br/> |
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interfaccia VIP interna del server perimetrale  <br/> |Qualsiasi  <br/> • Director  <br/> • Indirizzo VIP del pool di Director  <br/> • Server front-end  <br/> • Indirizzo VIP del pool Front-End  <br/> |Traffico SIP in ingresso verso il direttore, l'indirizzo VIP del pool di Director, il server front-end o l'indirizzo VIP del pool Front-end dall'interfaccia interna del server perimetrale.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Qualsiasi  <br/> • Indirizzo IP del server front-end  <br/> • Indirizzo IP del pool Front-End  <br/> • Qualsiasi Appliance Survivable Branch che usa questo Edge Server  <br/> • Qualsiasi Survivable Branch Server che usa questo Edge Server  <br/> |Interfaccia interna del server perimetrale  <br/> |Autenticazione degli utenti A/V dal server front-end o dal pool Front-end o dal Survivable Branch Appliance o Survivable Branch Server, usando il server perimetrale.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualsiasi  <br/> |Interfaccia interna del server perimetrale  <br/> |Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualsiasi  <br/> |Interfaccia VIP interna del server perimetrale  <br/> |Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni se la comunicazione UDP non funziona. TCP viene quindi usato per i trasferimenti di file e la condivisione desktop.  <br/> |
