---
title: Requisiti per la porta e il protocollo per i server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: "Riepilogo: esaminare le considerazioni sull'utilizzo della porta prima di implementare Skype for Business Server."
ms.openlocfilehash: ca790f2ca4ff1504ab4851fedfbba086e251d91a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802016"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Requisiti per la porta e il protocollo per i server
 
**Riepilogo:** Esaminare le considerazioni sull'utilizzo della porta prima di implementare Skype for Business Server.
  
Skype for Business Server richiede che siano aperte porte specifiche sui firewall esterni e interni. Inoltre, se l'organizzazione è distribuita in IPsec (Internet Protocol Security), IPsec deve essere disabilitato sull'intervallo di porte usate per il recapito di audio, video e video panoramico. 
  
Anche se all'inizio può sembrare un po' scoraggiante, il sollevamento di carichi pesanti per la pianificazione può essere eseguito usando lo [strumento di pianificazione di Skype for Business Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725). Dopo aver eseguito le domande della procedura guidata sulle caratteristiche che si prevede di usare, per ogni sito che si definisce è possibile visualizzare il report del firewall nel report amministratore Edge e usare le informazioni elencate per creare regole di yourfirewall. È anche possibile apportare modifiche a molti dei nomi e degli indirizzi IP usati, per informazioni dettagliate vedere [rivedere il report del firewall](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Tieni presente che puoi esportare il report amministratore Edge in un foglio di calcolo di Excel e il report del firewall sarà uno dei fogli di lavoro nel file. 
  
È anche possibile trovare le informazioni in queste tabelle in formato diagramma rivedendo il poster dei workload di protocollo collegato ai [diagrammi tecnici per l'articolo di Skype for Business Server 2015](../../technical-diagrams.md) .
> [!NOTE]
> - Se stai implementando Skype for business online (Office 365), consulta gli [URL e gli intervalli di indirizzi IP di Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). In ambienti ibridi sarà necessario fare riferimento a questo argomento e pianificare anche la [connettività ibrida](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
> - Si possono avere firewall hardware o software, ma non sono necessari modelli o versioni specifiche. Ciò che conta è ciò che le porte sono whitelist in modo che il firewall non comprometta il funzionamento di Skype for Business Server.
  
## <a name="port-and-protocol-details"></a>Dettagli sulla porta e sul protocollo

Questa sezione riepiloga le porte e i protocolli usati dai server, i bilanciatori di carico e i client in una distribuzione di Skype for Business Server.
  
> [!NOTE]
> Quando si avvia Skype for Business Server, vengono aperte le porte necessarie in Windows Firewall. Windows Firewall dovrebbe essere già in uso nella maggior parte delle applicazioni normali, ma se non viene usato, Skype for Business Server funzionerà senza. 
  
Per informazioni dettagliate sulla configurazione del firewall per i componenti Edge, vedere [scenari di Edge Server in Skype for Business server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
La tabella seguente elenca le porte che devono essere aperte in ogni ruolo del server interno. 
  
**Porte del server obbligatorie (per ruolo del server)**

|Ruolo del server|Nome servizio|Porta|Protocollo|Note|
|:-----|:-----|:-----|:-----|:-----|
|Tutti i server  |Browser SQL  |1434  |UDP  |Browser SQL per la copia replicata locale del database di Central Management store.  |
|Server front-end  |Servizio front-end di Skype for Business Server  |5060  |TCP  |È possibile usare facoltativamente i server standard e i server front-end per le route statiche a servizi attendibili, ad esempio i server di controllo delle chiamate remote.  |
|Server front-end  |Servizio front-end di Skype for Business Server  |5061  | TCP (TLS) |Usato dai server standard e dai pool Front-end per tutte le comunicazioni SIP interne tra server (MTLS), per le comunicazioni SIP tra server e client (TLS) e per le comunicazioni SIP tra server front-end e Mediation Server (MTLS). Usato anche per le comunicazioni con un server di monitoraggio.  |
| Server front-end |Servizio front-end di Skype for Business Server  |444  | HTTPS <br/> TCP  |Usato per la comunicazione HTTPS tra lo stato attiva (il componente Skype for Business Server che gestisce lo stato conferenza) e i singoli server.  <br/> Questa porta viene usata anche per la comunicazione TCP tra gli elettrodomestici Survivable Branch e i server front-end.  |
|Server front-end  |Servizio front-end di Skype for Business Server  |135  |DCOM e chiamata di procedura remota (RPC)  |Usato per operazioni basate su DCOM come lo spostamento di utenti, la sincronizzazione di User Replicator e la sincronizzazione della Rubrica.  |
|Server front-end  |Servizio di conferenza di messaggistica istantanea di Skype for Business Server  |5062  |TCP  |Usato per le richieste SIP in arrivo per le conferenze di messaggistica istantanea.  |
|Server front-end  |Servizio di conferenza Web di Skype for Business Server  |8057  |TCP (TLS)  |Usato per ascoltare le connessioni PSOM (Persistent Shared Object Model) dal client.  |
|Server front-end  |Servizio compatibilità con Skype for Business Server Web Conferencing  |8058  |TCP (TLS)  |Usato per ascoltare le connessioni PSOM (Persistent Shared Object Model) dal client Live Meeting e dalle versioni precedenti di Skype for Business Server.  |
|Server front-end  |Servizio di conferenza audio/video di Skype for Business Server  |5063  |TCP  |Usato per le richieste SIP in arrivo per le conferenze audio/video (A/V).  |
|Server front-end  |Servizio di conferenza audio/video di Skype for Business Server  |57501-65535  |TCP/UDP  |Intervallo di porte multimediali usato per i servizi di conferenza video.  |
|Server front-end  |Servizio compatibilità Web di Skype for Business Server  |80  |HTTP  |Usato per la comunicazione dai server front-end agli FQDN della Web farm (gli URL usati da IIS Web Components) quando non viene usato HTTPS.  |
|Server front-end  |Servizio compatibilità Web di Skype for Business Server  |443  |HTTPS  |Usato per la comunicazione dai server front-end agli FQDN della Web farm (gli URL usati da IIS Web Components).  |
|Server front-end  |Servizio compatibilità Web di Skype for Business Server  |8080  |TCP e HTTP  |Usato dai componenti Web per l'accesso esterno.  |
|Server front-end  |Componente server Web  |4443  |HTTPS  |HTTPS (da proxy inverso) e le comunicazioni inter-pool HTTPS front-end per l'accesso all'individuazione automatica.  |
|Server front-end  |Componente server Web  |8060  |TCP (MTLS)  ||
|Server front-end  |Componente server Web  |8061  |TCP (MTLS)  ||
|Server front-end  |Componente servizi mobili  |5086  |TCP (MTLS)  |Porta SIP usata dai processi interni dei servizi mobili  |
|Server front-end  |Componente servizi mobili  |5087  |TCP (MTLS)  |Porta SIP usata dai processi interni dei servizi mobili  |
|Server front-end  |Componente servizi mobili  |443  |HTTPS  ||
|Server front-end  |Servizio di conferenza telefonica di Skype for Business Server (servizi di conferenza telefonica con accesso esterno)  |5064  |TCP  |Usato per le richieste SIP in arrivo per i servizi di conferenza telefonica con accesso esterno.  |
|Server front-end  |Servizio di conferenza telefonica di Skype for Business Server (servizi di conferenza telefonica con accesso esterno)  |5072  |TCP  |Usato per le richieste SIP in arrivo per l'operatore (servizi di conferenza telefonica con accesso esterno).  |
|Server front-end che eseguono anche un Mediation Server collocato  |Servizio di mediazione di Skype for Business Server  |5070  |TCP  |Usato dal Mediation Server per le richieste in arrivo dal server front-end al Mediation Server.  |
|Server front-end che eseguono anche un Mediation Server collocato  |Servizio di mediazione di Skype for Business Server  |5067  |TCP (TLS)  |Usato per le richieste SIP in arrivo dal gateway PSTN al Mediation Server.  |
|Server front-end che eseguono anche un Mediation Server collocato  |Servizio di mediazione di Skype for Business Server  |5068  |TCP  |Usato per le richieste SIP in arrivo dal gateway PSTN al Mediation Server.  |
|Server front-end che eseguono anche un Mediation Server collocato  |Servizio di mediazione di Skype for Business Server  |5081  |TCP  |Usato per le richieste SIP in uscita dal server Mediation al gateway PSTN.  |
|Server front-end che eseguono anche un Mediation Server collocato  |Servizio di mediazione di Skype for Business Server  |5082  |TCP (TLS)  |Usato per le richieste SIP in uscita dal server Mediation al gateway PSTN.  |
|Server front-end  |Servizio di condivisione applicazioni di Skype for Business Server  |5065  |TCP  |Usato per le richieste di ascolto SIP in arrivo per la condivisione delle applicazioni.  |
|Server front-end  |Servizio di condivisione applicazioni di Skype for Business Server  |49152-65535  |TCP  |Intervallo di porte multimediali usato per la condivisione delle applicazioni.  |
|Server front-end  |Servizio di annuncio per conferenze di Skype for Business Server  |5073  |TCP  |Usato per le richieste SIP in arrivo per il servizio di annunci conferenza di Skype for Business Server (ovvero per i servizi di conferenza telefonica con accesso esterno).  |
|Server front-end  |Servizio di Call Park di Skype for Business Server  |5075  |TCP  |Usato per le richieste SIP in arrivo per l'applicazione Call Park.  |
|Server front-end  |Servizio test audio di Skype for Business Server  |5076  |TCP  |Usato per le richieste SIP in arrivo per il servizio di test audio.  |
|Server front-end  |Non applicabile  |5066  |TCP  |Usato per il gateway avanzato 9-1-1 (E9-1-1) in uscita.  |
|Server front-end  |Servizio Response Group di Skype for Business Server  |5071  |TCP  |Usato per le richieste SIP in arrivo per l'applicazione Response Group.  |
|Server front-end  |Servizio Response Group di Skype for Business Server  |8404  |TCP (MTLS)  |Usato per le richieste SIP in arrivo per l'applicazione Response Group.  |
|Server front-end  |Servizio criteri di larghezza di banda di Skype for Business Server  |5080  |TCP  |Usato per il controllo dell'ammissione tramite chiamata tramite il servizio criteri di larghezza di banda per il traffico a/V Edge TURN.  |
|Server front-end  |Accesso al server di condivisione file di Skype for Business Server  |445   |SMB/TCP  | Consente di recuperare la Rubrica, il contenuto della riunione e gli altri elementi archiviati nel server di condivisione file.  |
|Server front-end  |Servizio criteri di larghezza di banda di Skype for Business Server  |448  |TCP  |Usato per il controllo dell'ammissione tramite chiamata tramite il servizio criteri di larghezza di banda di Skype for Business Server.  |
|Server front-end in cui risiede l'Central Management store  | Servizio agente Master Replicator di Skype for Business Server |445  |TCP  |Usato per spingere i dati di configurazione da Central Management store ai server che usano Skype for Business Server.  |
|Tutti i server  |Browser SQL  |1434  |UDP  |Browser SQL per la copia replicata locale dei dati di Central Management store nell'istanza di SQL Server locale  |
|Tutti i server interni  |Vari  |49152-57500  |TCP/UDP  |Intervallo di porte multimediali usato per i servizi di audioconferenza in tutti i server interni. Usato da tutti i server che interrompono l'audio: Front End Servers (per il servizio di conferenza telefonica di Skype for Business Server, servizio di annuncio per conferenze di Skype for Business Server e servizio di conferenza audio/video di Skype for Business Server) e Mediation Server.  |
|Server di Office Web Apps  ||443  ||Usato da Skype for Business Server per connettersi al server di Office Web Apps.  |
|Consiglio  |Servizio front-end di Skype for Business Server  |5060  |TCP  |Facoltativamente usato per le route statiche a servizi attendibili, ad esempio i server di controllo delle chiamate remote.  |
|Consiglio  |Servizio front-end di Skype for Business Server  |444  |HTTPS  <br/> TCP  |Comunicazioni tra server tra front-end e Director. Inoltre, la pubblicazione del certificato client (per i server front-end) o la convalida se il certificato client è già stato pubblicato.  |
|Consiglio  |Servizio compatibilità Web di Skype for Business Server  |80  |TCP  |Usato per la comunicazione iniziale da Directors agli FQDN della Web farm (gli URL usati da IIS Web Components). In funzionamento normale si passa al traffico HTTPS usando la porta 443 e il protocollo TCP.  |
|Consiglio  |Servizio compatibilità Web di Skype for Business Server  |443  |HTTPS  |Usato per la comunicazione da Directors agli FQDN della Web farm (gli URL usati da IIS Web Components).  |
|Consiglio  |Servizio front-end di Skype for Business Server  |5061  |TCP  |Usato per le comunicazioni interne tra i server e per le connessioni client.  |
|Mediation Server  |Servizio di mediazione di Skype for Business Server  |5070  |TCP  |Usato dal Mediation Server per le richieste in arrivo dal server front-end.  |
|Mediation Server  |Servizio di mediazione di Skype for Business Server  |5067  |TCP (TLS)  |Usato per le richieste SIP in arrivo dal gateway PSTN.  |
|Mediation Server  |Servizio di mediazione di Skype for Business Server  |5068  |TCP  |Usato per le richieste SIP in arrivo dal gateway PSTN.  |
|Mediation Server  |Servizio di mediazione di Skype for Business Server  |5070  |TCP (MTLS)  |Usato per le richieste SIP provenienti dai server front-end.  |
|Server front end di chat persistente  |SIP chat persistente  |5041  |TCP (MTLS)  ||
|Server front end di chat persistente  |Chat persistente Windows Communication Foundation (WCF)  |881  |TCP (TLS) e TCP (MTLS)  ||
|Server front end di chat persistente  |Servizio di trasferimento file Chat persistente  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Alcuni scenari di controllo delle chiamate remote richiedono una connessione TCP tra il server front-end o il Director e il PBX. Anche se Skype for Business Server non usa più la porta TCP 5060, durante la distribuzione del controllo delle chiamate remote si crea una configurazione del server attendibile, che associa il nome di dominio completo del server RCC line alla porta TCP che il server o il direttore front-end userà per connettersi al Sistema PBX. Per informazioni dettagliate, vedere il cmdlet **CsTrustedApplicationComputer** nella documentazione di Skype for Business Server Management Shell.
  
Per i pool che usano solo il bilanciamento del carico hardware (non il bilanciamento del carico DNS), la tabella seguente mostra le porte che devono aprire i dispositivi di bilanciamento del carico hardware.
  
**Porte di bilanciamento del carico hardware se si usa solo il bilanciamento del carico hardware**

|Bilanciamento del carico|Porta|Protocollo|
|:-----|:-----|:-----|
|Bilanciamento del carico del server front-end  |5061  |TCP (TLS)  |
|Bilanciamento del carico del server front-end  |444  |HTTPS  |
|Bilanciamento del carico del server front-end  |135  |DCOM e chiamata di procedura remota (RPC)  |
|Bilanciamento del carico del server front-end  |80  |HTTP  |
|Bilanciamento del carico del server front-end  |8080  |TCP-client e recupero di dispositivi del certificato radice dal server front-end-client e dispositivi autenticati da NTLM  |
|Bilanciamento del carico del server front-end  |443  |HTTPS  |
|Bilanciamento del carico del server front-end  |4443  |HTTPS (da proxy inverso)  |
|Bilanciamento del carico del server front-end  |5072  |TCP  |
|Bilanciamento del carico del server front-end  |5073  |TCP  |
|Bilanciamento del carico del server front-end  |5075  |TCP  |
|Bilanciamento del carico del server front-end  |5076  |TCP  |
|Bilanciamento del carico del server front-end  |5071  |TCP  |
|Bilanciamento del carico del server front-end  |5080  |TCP  |
|Bilanciamento del carico del server front-end  |448  |TCP  |
|Bilanciamento del carico di Mediation Server  |5070  |TCP  |
|Bilanciamento del carico del server front-end (se il pool esegue anche Mediation Server)  |5070  |TCP  |
|Direttore di bilanciamento del carico  |443  |HTTPS  |
|Direttore di bilanciamento del carico  |444  |HTTPS  |
|Direttore di bilanciamento del carico  |5061  |TCP  |
|Direttore di bilanciamento del carico  |4443  |HTTPS (da proxy inverso)  |
   
I pool di front end e i pool di direttori che usano il bilanciamento del carico DNS devono essere distribuiti anche da un dispositivo di bilanciamento del carico hardware. La tabella seguente mostra le porte che devono essere aperte in questi dispositivi di bilanciamento del carico hardware.
  
**Porte di bilanciamento del carico hardware se si usa il bilanciamento del carico DNS**

|Bilanciamento del carico|Porta|Protocollo|
|:-----|:-----|:-----|
|Bilanciamento del carico del server front-end  |80  |HTTP  |
|Bilanciamento del carico del server front-end  |443  |HTTPS  |
|Bilanciamento del carico del server front-end  |8080  |TCP-client e recupero di dispositivi del certificato radice dal server front-end-client e dispositivi autenticati da NTLM  |
|Bilanciamento del carico del server front-end  |4443  |HTTPS (da proxy inverso)  |
|Direttore di bilanciamento del carico  |443  |HTTPS  |
|Direttore di bilanciamento del carico  |4443  |HTTPS (da proxy inverso)  |

**Porte client richieste**

|Componente|Porta|Protocollo|Note|
|:-----|:-----|:-----|:-----|
|Client  |67/68  |DHCP  |Usato da Skype for Business Server per trovare il nome di dominio completo del registrar, ovvero se DNS SRV non riesce e le impostazioni manuali non sono configurate.  |
|Client  |443  |TCP (TLS)  |Usato per il traffico SIP da client a server per l'accesso degli utenti esterni.  |
|Client  |443  |TCP (PSOM/TLS)  |Usato per l'accesso degli utenti esterni alle sessioni di conferenza Web.  |
|Client  |443  |TCP (STUN/MSTURN)  |Usato per l'accesso degli utenti esterni alle sessioni A/V e agli elementi multimediali (TCP)  |
|Client  |3478  |UDP (STUN/MSTURN)  |Usato per l'accesso degli utenti esterni alle sessioni A/V e agli elementi multimediali (UDP)  |
|Client  |5061  |TCP (MTLS)  |Usato per il traffico SIP da client a server per l'accesso degli utenti esterni.  |
|Client  |6891-6901  |TCP  |Usato per il trasferimento di file tra client Skype for business e client precedenti.  |
|Client  |1024-65535\*  |TCP/UDP  |Intervallo di porte audio (minimo 20 porte necessarie)  |
|Client  |1024-65535\*  |TCP/UDP  |Intervallo di porte video (è necessario un minimo di 20 porte).  |
|Client  |1024-65535\*  |TCP  |Trasferimento di file peer-to-peer (per il trasferimento di file di conferenza, i client usano PSOM).  |
|Client  |1024-65535\*  |TCP  |Condivisione applicazioni.  |
|Telefono per area comune Aastra 6721ip  <br/> Telefono da tavolo Aastra 6725ip  <br/> Telefono IP HP 4110 (telefono area comune)  <br/> Telefono IP HP 4120 (telefono da tavolo)  <br/> Telefono per area comune IP di Polycom CX500  <br/> Telefono da tavolo IP Polycom CX600  <br/> Telefono da tavolo IP Polycom CX700  <br/> Telefono per conferenze IP di Polycom CX3000  |67/68  |DHCP  |Usato dai dispositivi elencati per trovare il certificato di Skype for Business Server, il nome di dominio completo e il nome di dominio completo del registrar.  |
   
\*Per configurare porte specifiche per questi tipi di elementi multimediali, usare il cmdlet CsConferencingConfiguration (ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange Parameters).
  
> [!NOTE]
> Il programma di installazione per i client Skype for business crea automaticamente le eccezioni del firewall di sistema operativo necessarie nel computer client. 

> [!NOTE]
> Le porte usate per l'accesso degli utenti esterni sono necessarie per qualsiasi scenario in cui il client deve attraversare il firewall dell'organizzazione, ad esempio le comunicazioni esterne o le riunioni ospitate da altre organizzazioni. 
  
## <a name="ipsec-exceptions"></a>Eccezioni IPsec

Per le reti aziendali in cui è stato distribuito Internet Protocol Security (IPsec) (Vedi IETF RFC 4301-4309), IPsec deve essere disabilitato sull'intervallo di porte usate per il recapito di audio, video e video panoramico. La raccomandazione è motivata dalla necessità di evitare qualsiasi ritardo nell'allocazione delle porte multimediali a causa della negoziazione IPsec.
  
La tabella seguente illustra le impostazioni di eccezione IPsec consigliate. 
  
**Eccezioni IPsec consigliate**

|Nome regola|IP di origine|IP di destinazione|Protocollo|Porta di origine|Porta di destinazione|Requisito di autenticazione|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|A/V Edge Server Internal in ingresso  |Qualsiasi  |A/V Edge Server interno  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non eseguire l'autenticazione  |
|A/V Edge Server esterno in ingresso  |Qualsiasi  |A/V Edge Server esterno  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non eseguire l'autenticazione  |
|A/V Edge Server in uscita interna  |A/V Edge Server interno  |Qualsiasi  |TCP &amp; UDP  |Qualsiasi  |Qualsiasi  |Non eseguire l'autenticazione  |
|A/V Edge Server in uscita esterna  |A/V Edge Server esterno  |Qualsiasi  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non eseguire l'autenticazione  |
|Mediation Server in ingresso  |Qualsiasi  |Pubblicitari  <br/> Server (s)  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non eseguire l'autenticazione  |
|Mediation Server in uscita  |Pubblicitari  <br/> Server (s)  |Qualsiasi  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non eseguire l'autenticazione  |
|Operatore di conferenza in ingresso  |Qualsiasi  |Server front-end con l'operatore di conferenza  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non eseguire l'autenticazione  |
|Operatore di conferenza in uscita  |Server front-end con l'operatore di conferenza  |Qualsiasi  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non eseguire l'autenticazione  |
|A/V Conferencing in ingresso  |Qualsiasi  |Server front-end  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non eseguire l'autenticazione  |
|A/V Conferencing in uscita  |Server front-end  |Qualsiasi  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non eseguire l'autenticazione  |
|Exchange in ingresso  |Qualsiasi  |Messaggistica unificata di Exchange  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non eseguire l'autenticazione  |
|Server di condivisione applicazioni in ingresso  |Qualsiasi  |Server di condivisione applicazioni  |TCP  |Qualsiasi  |Qualsiasi  |Non eseguire l'autenticazione  |
|Server di condivisione applicazioni in uscita  |Server di condivisione applicazioni  |Qualsiasi  |TCP  |Qualsiasi  |Qualsiasi  |Non eseguire l'autenticazione  |
|Exchange in uscita  |Messaggistica unificata di Exchange  |Qualsiasi  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non eseguire l'autenticazione  |
|Client  |Qualsiasi  |Qualsiasi  |UDP  |Intervallo di porte multimediali specificato  |Qualsiasi  |Non eseguire l'autenticazione  |
