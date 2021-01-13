---
title: Requisiti relativi a porte e protocolli per i server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: "Riepilogo: esaminare le considerazioni sull'utilizzo delle porte prima di implementare Skype for Business Server."
ms.openlocfilehash: 227fcbccf815886c5afa55c843ba59688f471a29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834306"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Requisiti relativi a porte e protocolli per i server
 
**Riepilogo:** Esaminare le considerazioni sull'utilizzo delle porte prima di implementare Skype for Business Server.
  
Skype for Business Server richiede che vengano aperte porte specifiche sui firewall esterni e interni. Se nell'organizzazione viene distribuita IPsec (Internet Protocol Security), IPsec deve essere disabilitato nell'intervallo di porte utilizzate per il recapito di audio, video e video panoramici. 
  
Anche se questo può sembrare un po' scoraggiante all'inizio, il sollevamento di carichi pesanti per la pianificazione può essere effettuato utilizzando lo [strumento di pianificazione di Skype for Business Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725). Dopo aver completato le domande della procedura guidata sulle caratteristiche che si intende utilizzare, per ogni sito definito è possibile visualizzare il report del firewall all'interno del rapporto di amministrazione del server perimetrale e utilizzare le informazioni riportate di seguito per creare le regole di yourfirewall. Per ulteriori informazioni, vedere [rivedere il report sul firewall](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report)...... Tenere presente che è possibile esportare il report amministratore Edge in un foglio di calcolo di Excel e il report del firewall sarà uno dei fogli di lavoro nel file. 
  
È inoltre possibile trovare le informazioni contenute in queste tabelle in formato diagramma rivedendo il poster dei carichi di lavoro del protocollo collegato ai [diagrammi tecnici per l'articolo di Skype for Business Server 2015](../../technical-diagrams.md) .
> [!NOTE]
> - Se si sta implementando Skype for business online (Microsoft 365 o Office 365), fare riferimento a [microsoft 365 e agli intervalli di indirizzi IP e URL di office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). Gli ambienti ibridi devono fare riferimento a questo argomento e [pianificare anche la connettività ibrida](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
> - È possibile disporre di firewall hardware o software, non sono necessari modelli o versioni specifiche. Ciò che conta è ciò che le porte sono whitelist in modo che il firewall non comprometta il funzionamento di Skype for Business Server.
  
## <a name="port-and-protocol-details"></a>Informazioni dettagliate sulle porte e sui protocolli

In questa sezione vengono riepilogate le porte e i protocolli utilizzati dai server, dai bilanciamento del carico e dai client in una distribuzione di Skype for Business Server.
  
> [!NOTE]
> Quando viene avviato Skype for Business Server, vengono aperte le porte necessarie nel firewall di Windows. Windows Firewall dovrebbe essere già in esecuzione nella maggior parte delle applicazioni normali, ma se non viene utilizzato, Skype for Business Server funzionerà senza. 
  
Per informazioni dettagliate sulla configurazione del firewall per i componenti perimetrali, vedere [Edge server scenarios in Skype for Business server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
Nella tabella seguente sono elencate le porte che è necessario aprire per ogni ruolo server interno. 
  
**Porte server richieste (per ruolo server)**

|Ruolo server|Nome servizio|Porta|Protocollo|Note|
|:-----|:-----|:-----|:-----|:-----|
|Tutti i server  |SQL Browser  |1434  |UDP  |Browser SQL per la copia locale replicata del database dell'archivio di gestione centrale.  |
|Front End Server  |Servizio Front-End di Skype for Business Server  |5060  |TCP  |Utilizzata facoltativamente dai server Standard Edition e dai Front End Server per le route statiche ai servizi trusted, ad esempio i server di controllo delle chiamate remote.  |
|Front End Server  |Servizio Front-End di Skype for Business Server  |5061  | TCP (TLS) |Utilizzato dai server Standard Edition e dai pool Front end per tutte le comunicazioni SIP interne tra server (MTLS), per le comunicazioni SIP tra server e client (TLS) e per le comunicazioni SIP tra front end server e Mediation Server (MTLS). Utilizzato anche per le comunicazioni con un Monitoring Server.  |
| Front End Server |Servizio Front-End di Skype for Business Server  |444  | HTTPS <br/> TCP  |Utilizzato per la comunicazione HTTPS tra lo stato attivo (il componente Skype for Business Server che gestisce lo stato della conferenza) e i singoli server.  <br/> Questa porta viene utilizzata anche per le comunicazioni TCP tra Survivable Branch Appliances e front end server.  |
|Front End Server  |Servizio Front-End di Skype for Business Server  |135  |DCOM e RPC (Remote Procedure Call)  |Utilizzata per le operazioni basate su DCOM quali spostamento utenti, sincronizzazione User Replicator e sincronizzazione rubrica.  |
|Front End Server  |Servizio di messaggistica istantanea di Skype for Business Server  |5062  |TCP  |Utilizzata per le richieste SIP in arrivo per le conferenze di messaggistica istantanea (IM).  |
|Front End Server  |Servizio Web Conferencing di Skype for Business Server  |8057  |TCP (TLS)  |Utilizzata per attendere le connessioni PSOM (Persistent Shared Object Model) dal client.  |
|Front End Server  |Servizio compatibilità Web Conferencing di Skype for Business Server  |8058  |TCP (TLS)  |Utilizzato per l'attesa per le connessioni PSOM (Persistent Shared Object Model) dal client Live Meeting e le versioni precedenti di Skype for Business Server.  |
|Front End Server  |Servizio audio/video Conferencing di Skype for Business Server  |5063  |TCP  |Utilizzata per le richieste SIP in arrivo per Audio/Video (A/V) Conferencing.  |
|Front End Server  |Servizio audio/video Conferencing di Skype for Business Server  |57501-65535  |TCP/UDP  |Intervallo di porte di attesa multimediali utilizzato per le conferenze video.  |
|Front End Server  |Servizio compatibilità Web di Skype for Business Server  |80  |HTTP  |Utilizzata per le comunicazioni dai Front End Server ai nomi di dominio completi della Web farm (gli URL utilizzati dai componenti Web IIS) quando non si utilizzano protocolli HTTPS.  |
|Front End Server  |Servizio compatibilità Web di Skype for Business Server  |443  |HTTPS  |Utilizzata per le comunicazioni dai Front End Server ai nomi di dominio completi della Web farm (gli URL utilizzati dai componenti Web IIS).  |
|Front End Server  |Servizio compatibilità Web di Skype for Business Server  |8080  |TCP e HTTP  |Utilizzato dai componenti Web per l'accesso esterno.  |
|Front End Server  |Componente del server Web  |4443  |HTTPS  |HTTPS (da proxy inverso) e comunicazioni inter-pool HTTPS front-end per l'accesso all'individuazione automatica.  |
|Front End Server  |Componente del server Web  |8060  |TCP (MTLS)  ||
|Front End Server  |Componente del server Web  |8061  |TCP (MTLS)  ||
|Front End Server  |Componente dei servizi per dispositivi mobili  |5086  |TCP (MTLS)  |Porta SIP utilizzata dai processi interni dei servizi per dispositivi mobili  |
|Front End Server  |Componente dei servizi per dispositivi mobili  |5087  |TCP (MTLS)  |Porta SIP utilizzata dai processi interni dei servizi per dispositivi mobili  |
|Front End Server  |Componente dei servizi per dispositivi mobili  |443  |HTTPS  ||
|Front End Server  |Skype for Business Server Conferencing Attendant (servizi di conferenza telefonica con accesso esterno)  |5064  |TCP  |Utilizzata per le richieste SIP in arrivo per le conferenze telefoniche con accesso esterno.  |
|Front End Server  |Skype for Business Server Conferencing Attendant (servizi di conferenza telefonica con accesso esterno)  |5072  |TCP  |Utilizzato per le richieste SIP in arrivo per Attendant (servizi di conferenza telefonica con accesso esterno).  |
|Front End Server che eseguono anche un Mediation Server collocato  |Servizio Mediation Server di Skype for business  |5070  |TCP  |Utilizzata dal Mediation Server per le richieste in arrivo dal Front End Server al Mediation Server.  |
|Front End Server che eseguono anche un Mediation Server collocato  |Servizio Mediation Server di Skype for business  |5067  |TCP (TLS)  |Utilizzata per le richieste SIP in arrivo dal gateway PSTN al Mediation Server.  |
|Front End Server che eseguono anche un Mediation Server collocato  |Servizio Mediation Server di Skype for business  |5068  |TCP  |Utilizzata per le richieste SIP in arrivo dal gateway PSTN al Mediation Server.  |
|Front End Server che eseguono anche un Mediation Server collocato  |Servizio Mediation Server di Skype for business  |5081  |TCP  |Utilizzata per le richieste SIP in uscita dal Mediation Server al gateway PSTN.  |
|Front End Server che eseguono anche un Mediation Server collocato  |Servizio Mediation Server di Skype for business  |5082  |TCP (TLS)  |Utilizzata per le richieste SIP in uscita dal Mediation Server al gateway PSTN.  |
|Front End Server  |Servizio di condivisione applicazioni di Skype for Business Server  |5065  |TCP  |Utilizzata per le richieste di attesa SIP in arrivo per la condivisione delle applicazioni.  |
|Front End Server  |Servizio di condivisione applicazioni di Skype for Business Server  |49152-65535  |TCP  |Intervallo di porte di attesa multimediali per la condivisione delle applicazioni.  |
|Front End Server  |Servizio annuncio di Skype for Business Server  |5073  |TCP  |Utilizzato per le richieste SIP in arrivo per il servizio Annuncio conferenza di Skype for Business Server (ovvero per le conferenze telefoniche con accesso esterno).  |
|Front End Server  |Servizio parcheggio di chiamata di Skype for Business Server  |5075  |TCP  |Utilizzata per le richieste SIP in arrivo per l'applicazione Parcheggio di chiamata.  |
|Front End Server  |Servizio di test audio di Skype for Business Server  |5076  |TCP  |Utilizzata per le richieste SIP in arrivo per il servizio Test audio.  |
|Front End Server  |Non applicabile  |5066  |TCP  |Utilizzata per il gateway Enhanced 9-1-1 (E9-1-1) in uscita.  |
|Front End Server  |Servizio Response Group di Skype for Business Server  |5071  |TCP  |Utilizzata per le richieste SIP in arrivo per l'applicazione Response Group.  |
|Front End Server  |Servizio Response Group di Skype for Business Server  |8404  |TCP (MTLS)  |Utilizzata per le richieste SIP in arrivo per l'applicazione Response Group.  |
|Front End Server  |Servizio criteri di larghezza di banda di Skype for Business Server  |5080  |TCP  |Utilizzata per il controllo di ammissione di chiamata eseguito dal servizio criteri larghezza di banda per il traffico A/V Edge TURN.  |
|Front End Server  |Accesso al server di condivisione file di Skype for Business Server  |445   |SMB/TCP  | Utilizzato per recuperare la Rubrica, il contenuto delle riunioni e gli altri elementi archiviati nel server di condivisione file.  |
|Front End Server  |Servizio criteri di larghezza di banda di Skype for Business Server  |448  |TCP  |Utilizzato per il controllo di ammissione di chiamata dal servizio criteri di larghezza di banda di Skype for Business Server.  |
|Server front end in cui si trova l'archivio di gestione centrale  | Servizio agente Master Replicator di Skype for Business Server |445  |TCP  |Utilizzato per inviare i dati di configurazione dall'archivio di gestione centrale ai server che eseguono Skype for Business Server.  |
|Tutti i server  |SQL Browser  |1434  |UDP  |SQL browser per la copia locale replicata dei dati dell'archivio di gestione centrale nell'istanza locale di SQL Server  |
|Tutti i server interni  |Vari  |49152-57500  |TCP/UDP  |Intervallo di porte multimediali utilizzato per le conferenze audio su tutti i server interni. Utilizzato da tutti i server che terminano audio: Front End Server (per il servizio Operatore Conferenza di Skype for Business Server, servizio annuncio per conferenze di Skype for Business Server e servizio di conferenza audio/video per Skype for Business Server) e Mediation Server.  |
|Server Office Web Apps  ||443  ||Utilizzato da Skype for Business Server per la connessione al server Office Web Apps.  |
|Amministrazione  |Servizio Front-End di Skype for Business Server  |5060  |TCP  |Utilizzata facoltativamente per le route statiche ai servizi trusted, come i server di controllo delle chiamate remote.  |
|Amministrazione  |Servizio Front-End di Skype for Business Server  |444  |HTTPS  <br/> TCP  |Comunicazioni interne ai server tra Front End e Director. È inoltre possibile pubblicare il certificato client (nei Front End Server) o convalidare se il certificato client è già stato pubblicato.  |
|Amministrazione  |Servizio compatibilità Web di Skype for Business Server  |80  |TCP  |Utilizzata per le comunicazioni iniziali dai Director ai nomi di dominio completo (FQDN) della Web farm (gli URL utilizzati dai componenti Web IIS). Durante il normale funzionamento, viene effettuato il passaggio al traffico HTTPS mediante la porta 443 e il tipo di protocollo TCP.  |
|Amministrazione  |Servizio compatibilità Web di Skype for Business Server  |443  |HTTPS  |Utilizzata per le comunicazioni dai Director ai nomi di dominio completi (FQDN) della Web farm (gli URL utilizzati dai componenti Web IIS).  |
|Amministrazione  |Servizio Front-End di Skype for Business Server  |5061  |TCP  |Utilizzata per le comunicazioni interne tra i server e per le connessioni client.  |
|Mediation Server  |Servizio Mediation Server di Skype for business  |5070  |TCP  |Utilizzata dal Mediation Server per le richieste in arrivo dal Front End Server.  |
|Mediation Server  |Servizio Mediation Server di Skype for business  |5067  |TCP (TLS)  |Utilizzata per le richieste SIP in arrivo dal gateway PSTN.  |
|Mediation Server  |Servizio Mediation Server di Skype for business  |5068  |TCP  |Utilizzata per le richieste SIP in arrivo dal gateway PSTN.  |
|Mediation Server  |Servizio Mediation Server di Skype for business  |5070  |TCP (MTLS)  |Utilizzata per le richieste SIP dai Front End Server.  |
|Front End Server della chat persistente  |SIP chat persistente  |5041  |TCP (MTLS)  ||
|Front End Server della chat persistente  |Chat persistente Windows Communication Foundation (WCF)  |881  |TCP (TLS) e TCP (MTLS)  ||
|Front End Server della chat persistente  |Servizio di trasferimento file di chat persistente  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Alcuni scenari di controllo delle chiamate remote richiedono una connessione TCP tra il Front End Server o Director e il sistema PBX. Anche se Skype for Business Server non utilizza più la porta TCP 5060, durante la distribuzione del controllo delle chiamate remote viene creata una configurazione del server attendibile, che associa il nome di dominio completo del server della linea RCC alla porta TCP che verrà utilizzata dal front end server o dal Director per la connessione al sistema PBX. Per informazioni dettagliate, vedere il cmdlet **CsTrustedApplicationComputer** nella documentazione di Skype for Business Server Management Shell.
  
Per i pool che utilizzano solo il servizio di bilanciamento del carico hardware (non il servizio di bilanciamento del carico DNS), la tabella che segue mostra le porte che devono aprire i servizi di bilanciamento del carico hardware.
  
**Porte del servizio di bilanciamento del carico hardware se si utilizza solo questo servizio di bilanciamento**

|Servizio di bilanciamento del carico|Porta|Protocollo|
|:-----|:-----|:-----|
|Servizio di bilanciamento del carico Front End Server  |5061  |TCP (TLS)  |
|Servizio di bilanciamento del carico Front End Server  |444  |HTTPS  |
|Servizio di bilanciamento del carico Front End Server  |135  |DCOM ed RPC (Remote Procedure Call)  |
|Servizio di bilanciamento del carico Front End Server  |80  |HTTP  |
|Servizio di bilanciamento del carico Front End Server  |8080  |TCP-client e recupero di dispositivi del certificato radice dal server front-end-client e dispositivi autenticati da NTLM  |
|Servizio di bilanciamento del carico Front End Server  |443  |HTTPS  |
|Servizio di bilanciamento del carico Front End Server  |4443  |HTTPS (da proxy inverso)  |
|Servizio di bilanciamento del carico Front End Server  |5072  |TCP  |
|Servizio di bilanciamento del carico Front End Server  |5073  |TCP  |
|Servizio di bilanciamento del carico Front End Server  |5075  |TCP  |
|Servizio di bilanciamento del carico Front End Server  |5076  |TCP  |
|Servizio di bilanciamento del carico Front End Server  |5071  |TCP  |
|Servizio di bilanciamento del carico Front End Server  |5080  |TCP  |
|Servizio di bilanciamento del carico Front End Server  |448  |TCP  |
|Bilanciamento del carico di Mediation Server  |5070  |TCP  |
|Bilanciamento del carico del server front-end (se il pool esegue anche Mediation Server)  |5070  |TCP  |
|Servizio di bilanciamento del carico Director  |443  |HTTPS  |
|Servizio di bilanciamento del carico Director  |444  |HTTPS  |
|Servizio di bilanciamento del carico Director  |5061  |TCP  |
|Servizio di bilanciamento del carico Director  |4443  |HTTPS (da proxy inverso)  |
   
È necessario che anche nei pool Front End e server Director che utilizzano il servizio di bilanciamento del carico DNS sia distribuito un servizio di bilanciamento del carico hardware. Nella tabella che segue sono indicate le porte che è necessario aprire in questi servizi di bilanciamento del carico hardware.
  
**Porte del servizio di bilanciamento del carico hardware se si utilizza il servizio di bilanciamento del carico DNS**

|Servizio di bilanciamento del carico|Porta|Protocollo|
|:-----|:-----|:-----|
|Servizio di bilanciamento del carico Front End Server  |80  |HTTP  |
|Servizio di bilanciamento del carico Front End Server  |443  |HTTPS  |
|Servizio di bilanciamento del carico Front End Server  |8080  |TCP-client e recupero di dispositivi del certificato radice dal server front-end-client e dispositivi autenticati da NTLM  |
|Servizio di bilanciamento del carico Front End Server  |4443  |HTTPS (da proxy inverso)  |
|Servizio di bilanciamento del carico Director  |443  |HTTPS  |
|Servizio di bilanciamento del carico Director  |4443  |HTTPS (da proxy inverso)  |

**Porte client richieste**

|Componente|Porta|Protocollo|Note|
|:-----|:-----|:-----|:-----|
|Client  |67/68  |DHCP  |Utilizzato da Skype for Business Server per individuare il nome di dominio completo del registrar (ovvero se DNS SRV ha esito negativo e le impostazioni manuali non sono configurate).  |
|Client  |443  |TCP (TLS)  |Utilizzata per il traffico SIP da client a server per l'accesso utente esterno.  |
|Client  |443  |TCP (PSOM/TLS)  |Utilizzata per l'accesso utente esterno alle sessioni di Web Conferencing.  |
|Client  |443  |TCP (STUN/MSTURN)  |Utilizzata per l'accesso utente esterno alle sessioni A/V e ai supporti multimediali (TCP)  |
|Client  |3478  |UDP (STUN/MSTURN)  |Utilizzato per l'accesso degli utenti esterni alle sessioni A/V e ai supporti (UDP)  |
|Client  |5061  |TCP (MTLS)  |Utilizzata per il traffico SIP da client a server per l'accesso utente esterno.  |
|Client  |6891-6901  |TCP  |Utilizzato per il trasferimento di file tra i client Skype for business e i client precedenti.  |
|Client  |1024-65535 \*  |TCP/UDP  |Intervallo di porte audio (almeno 20 porte richieste)  |
|Client  |1024-65535 \*  |TCP/UDP  |Intervallo di porte video (almeno 20 porte richieste).  |
|Client  |1024-65535 \*  |TCP  |Trasferimento file peer-to-peer (per il trasferimento dei file del servizio di conferenza, i client utilizzano PSOM).  |
|Client  |1024-65535 \*  |TCP  |Condivisione applicazioni.  |
|Telefono di area comune Aastra 6721ip  <br/> Telefono da tavolo Aastra 6725ip  <br/> Telefono IP HP 4110 (telefono di area comune)  <br/> Telefono IP HP 4120 (telefono da tavolo)  <br/> Telefono di area comune IP Polycom CX500  <br/> Telefono da tavolo IP Polycom CX600  <br/> Telefono da tavolo IP Polycom CX700  <br/> Telefono IP per conferenze Polycom CX3000  |67/68  |DHCP  |Utilizzato dai dispositivi elencati per trovare il certificato di Skype for Business Server, il nome FQDN del provisioning e il nome di dominio completo del registrar.  |
   
\* Per configurare porte specifiche per questi tipi di supporti, utilizzare il cmdlet CsConferencingConfiguration (parametri ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange).
  
> [!NOTE]
> I programmi di installazione per i client Skype for business creano automaticamente le eccezioni del firewall del sistema operativo necessarie sul computer client. 

> [!NOTE]
> Le porte utilizzate per l'accesso degli utenti esterni sono necessarie per tutti gli scenari in cui il client deve attraversare il firewall dell'organizzazione, ad esempio le comunicazioni esterne o le riunioni ospitate da altre organizzazioni. 
  
## <a name="ipsec-exceptions"></a>Eccezioni IPsec

Per le reti aziendali in cui è stato distribuito IPsec (Internet Protocol Security) (vedere IETF RFC 4301-4309), è necessario disabilitare IPsec nell'intervallo di porte utilizzate per il recapito di video audio, video e panoramici. Questa richiesta nasce dall'esigenza di evitare ritardi nell'allocazione delle porte multimediali a causa della negoziazione IPsec.
  
Nella tabella riportata di seguito vengono illustrate le impostazioni di eccezione IPsec consigliate. 
  
**Eccezioni IPsec consigliate**

|Nome regola|IP origine|IP destinazione|Protocollo|Porta origine|Porta destinazione|Requisito di autenticazione|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|A/V Edge Server in ingresso interno  |Qualsiasi  |A/V Edge Server interno  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|A/V Edge Server in ingresso esterno  |Qualsiasi  |A/V Edge Server esterno  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|A/V Edge Server interno in uscita  |A/V Edge Server interno  |Qualsiasi  |&amp;TCP UDP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|A/V Edge Server esterno in uscita  |A/V Edge Server esterno  |Qualsiasi  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Mediation Server in ingresso  |Qualsiasi  |Mediation  <br/> Server (s)  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Mediation Server in uscita  |Mediation  <br/> Server (s)  |Qualsiasi  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Operatore Conferenza in ingresso  |Qualsiasi  |Front End Server con Operatore Conferenza  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Operatore Conferenza in uscita  |Front End Server con Operatore Conferenza  |Qualsiasi  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|A/V Conferencing Server in ingresso  |Qualsiasi  |Front End Server  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|A/V Conferencing in uscita  |Front End Server  |Qualsiasi  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Exchange in ingresso  |Qualsiasi  |Messaggistica unificata di Exchange  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Server di condivisione applicazioni in ingresso  |Qualsiasi  |Server di condivisione applicazioni  |TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Server di condivisione applicazioni in uscita  |Server di condivisione applicazioni  |Qualsiasi  |TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Exchange in uscita  |Messaggistica unificata di Exchange  |Qualsiasi  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Client  |Qualsiasi  |Qualsiasi  |UDP  |Intervallo porte multimediali specificato  |Qualsiasi  |Non autenticare  |
