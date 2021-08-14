---
title: Requisiti di porta e protocollo per i server
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
ms.openlocfilehash: d2e3cf07dbdf7471cd1e2f535d619e8bece74ecc0a9f9e16d416b7cba46548c1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54352624"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Requisiti di porta e protocollo per i server
 
**Riepilogo:** Esaminare le considerazioni sull'utilizzo delle porte prima di implementare Skype for Business Server.
  
Skype for Business Server che porte specifiche nei firewall esterni e interni siano aperte. Inoltre, se nell'organizzazione è distribuito Internet Protocol Security (IPsec), IPsec deve essere disabilitato nell'intervallo di porte utilizzate per la distribuzione di audio, video e video panoramici. 
  
Anche se questo può sembrare un po' scoraggiante, l'attività di pianificazione può essere eseguita utilizzando lo strumento di pianificazione Skype for Business Server [2015.](https://go.microsoft.com/fwlink/p/?LinkID=282725) Dopo aver seguito le domande della procedura guidata sulle funzionalità che si prevede di utilizzare, per ogni sito definito è possibile visualizzare il Report firewall all'interno del report di amministrazione edge e utilizzare le informazioni elencate per creare le regole del firewall. È inoltre possibile apportare modifiche a molti dei nomi e degli indirizzi IP utilizzati, per informazioni dettagliate, vedere [Review the Firewall Report](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Tenere presente che è possibile esportare il report di amministrazione di Edge in un foglio di calcolo di Excel e il Report firewall sarà uno dei fogli di lavoro nel file. 
  
Le informazioni contenute in queste tabelle sono disponibili sotto forma di diagramma esaminando il poster Protocol Workloads collegato all'articolo [Technical diagrams for Skype for Business Server 2015.](../../technical-diagrams.md)

> [!NOTE]
> - Se stai implementando Skype for Business Online (Microsoft 365 o Office 365) fai riferimento a URL Microsoft 365 e Office 365 e intervalli [di indirizzi IP.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US) Gli ambienti ibridi dovranno fare riferimento a questo argomento e pianificare [anche la connettività ibrida.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2floc.json&toc=%2fSkypeForBusiness%2ftoc.json)
> - È possibile disporre di firewall hardware o software. Non sono necessari modelli o versioni specifici. Ciò che conta è quali porte vengono aggiunte a un elenco di indirizzi consentiti in modo che il firewall non comprometti il funzionamento di Skype for Business Server.
  
## <a name="port-and-protocol-details"></a>Informazioni dettagliate sulle porte e sui protocolli

In questa sezione vengono riepilogate le porte e i protocolli utilizzati da server, servizi di bilanciamento del carico e client in una Skype for Business Server distribuzione.
  
> [!NOTE]
> Quando Skype for Business Server, apre le porte necessarie nel firewall Windows firewall. Windows Il firewall dovrebbe essere già in esecuzione nella maggior parte delle applicazioni normali, ma se non viene utilizzato Skype for Business Server funzionerà senza di esso. 
  
Per informazioni dettagliate sulla configurazione del firewall per i componenti perimetrali, vedere [Edge Server scenarios in Skype for Business Server 2015.](../../plan-your-deployment/edge-server-deployments/scenarios.md) 
  
Nella tabella seguente sono elencate le porte che è necessario aprire per ogni ruolo server interno. 
  
**Porte server richieste (per ruolo server)**

|Ruolo server|Nome servizio|Porta|Protocollo|Note|
|:-----|:-----|:-----|:-----|:-----|
|Tutti i server  |SQL Browser  |1434  |UDP  |SQL Browser per la copia replicata locale del database dell'archivio di gestione centrale.  |
|Front-End Server  |Skype for Business Server Front-End servizio  |5060  |TCP  |Utilizzata facoltativamente dai server Standard Edition e dai Front End Server per le route statiche ai servizi trusted, ad esempio i server di controllo delle chiamate remote.  |
|Front End Server  |Skype for Business Server Front-End servizio  |5061  | TCP (TLS) |Utilizzato dai server edizione Standard e dai pool Front End per tutte le comunicazioni SIP interne tra server (MTLS), per le comunicazioni SIP tra server e client (TLS) e per le comunicazioni SIP tra Front End Server e Mediation Server (MTLS). Utilizzato anche per le comunicazioni con un Monitoring Server.  |
| Front End Server |Skype for Business Server Front-End servizio  |444  | HTTPS <br/> TCP  |Usato per la comunicazione HTTPS tra lo stato attivo (il componente Skype for Business Server che gestisce lo stato della conferenza) e i singoli server.  <br/> Questa porta viene utilizzata anche per le comunicazioni TCP tra Survivable Branch Appliance e Front End Server.  |
|Front End Server  |Skype for Business Server Front-End servizio  |135  |DCOM e RPC (Remote Procedure Call)  |Utilizzata per le operazioni basate su DCOM quali spostamento utenti, sincronizzazione User Replicator e sincronizzazione rubrica.  |
|Front End Server  |Skype for Business Server Servizio di conferenza di messaggistica istantanea  |5062  |TCP  |Utilizzata per le richieste SIP in arrivo per le conferenze di messaggistica istantanea (IM).  |
|Front End Server  |Skype for Business Server Servizio Web Conferencing  |8057  |TCP (TLS)  |Utilizzata per attendere le connessioni PSOM (Persistent Shared Object Model) dal client.  |
|Front End Server  |Skype for Business Server Servizio Compatibilità conferenze Web  |8058  |TCP (TLS)  |Utilizzato per ascoltare le connessioni PSOM (Persistent Shared Object Model) dal client Live Meeting e dalle versioni precedenti di Skype for Business Server.  |
|Front End Server  |Skype for Business Server Servizio audio/videoconferenza  |5063  |TCP  |Utilizzata per le richieste SIP in arrivo per Audio/Video (A/V) Conferencing.  |
|Front End Server  |Skype for Business Server Servizio audio/videoconferenza  |57501-65535  |TCP/UDP  |Intervallo di porte di attesa multimediali utilizzato per le conferenze video.  |
|Front End Server  |Skype for Business Server Servizio Compatibilità Web  |80  |HTTP  |Utilizzata per le comunicazioni dai Front End Server ai nomi di dominio completi della Web farm (gli URL utilizzati dai componenti Web IIS) quando non si utilizzano protocolli HTTPS.  |
|Front End Server  |Skype for Business Server Servizio Compatibilità Web  |443  |HTTPS  |Utilizzata per le comunicazioni dai Front End Server ai nomi di dominio completi della Web farm (gli URL utilizzati dai componenti Web IIS).  |
|Front End Server  |Skype for Business Server Servizio Compatibilità Web  |8080  |TCP e HTTP  |Utilizzato dai componenti Web per l'accesso esterno.  |
|Front End Server  |Componente server Web  |4443  |HTTPS  |Https (da proxy inverso) e comunicazioni tra pool Front End HTTPS per l'accesso di individuazione automatica.  |
|Front End Server  |Componente server Web  |8060  |TCP (MTLS)  ||
|Front End Server  |Componente server Web  |8061  |TCP (MTLS)  ||
|Front End Server  |Componente Servizi per dispositivi mobili  |5086  |TCP (MTLS)  |Porta SIP utilizzata dai processi interni di Servizi per dispositivi mobili  |
|Front End Server  |Componente Servizi per dispositivi mobili  |5087  |TCP (MTLS)  |Porta SIP utilizzata dai processi interni di Servizi per dispositivi mobili  |
|Front End Server  |Componente Servizi per dispositivi mobili  |443  |HTTPS  ||
|Front End Server  |Skype for Business Server Operatore conferenza (conferenza telefonica con accesso esterno)  |5064  |TCP  |Utilizzata per le richieste SIP in arrivo per le conferenze telefoniche con accesso esterno.  |
|Front End Server  |Skype for Business Server Operatore conferenza (conferenza telefonica con accesso esterno)  |5072  |TCP  |Utilizzato per le richieste SIP in arrivo per l'operatore (conferenza telefonica con accesso esterno).  |
|Front End Server che eseguono anche un Mediation Server collocato  |Skype for Business Server Mediation Service  |5070  |TCP  |Utilizzata dal Mediation Server per le richieste in arrivo dal Front End Server al Mediation Server.  |
|Front End Server che eseguono anche un Mediation Server collocato  |Skype for Business Server Mediation Service  |5067  |TCP (TLS)  |Utilizzata per le richieste SIP in arrivo dal gateway PSTN al Mediation Server.  |
|Front End Server che eseguono anche un Mediation Server collocato  |Skype for Business Server Mediation Service  |5068  |TCP  |Utilizzata per le richieste SIP in arrivo dal gateway PSTN al Mediation Server.  |
|Front End Server che eseguono anche un Mediation Server collocato  |Skype for Business Server Mediation Service  |5081  |TCP  |Utilizzata per le richieste SIP in uscita dal Mediation Server al gateway PSTN.  |
|Front End Server che eseguono anche un Mediation Server collocato  |Skype for Business Server Mediation Service  |5082  |TCP (TLS)  |Utilizzata per le richieste SIP in uscita dal Mediation Server al gateway PSTN.  |
|Front End Server  |Skype for Business Server Servizio condivisione applicazioni  |5065  |TCP  |Utilizzata per le richieste di attesa SIP in arrivo per la condivisione delle applicazioni.  |
|Front End Server  |Skype for Business Server Servizio condivisione applicazioni  |49152-65535  |TCP  |Intervallo di porte di attesa multimediali per la condivisione delle applicazioni.  |
|Front End Server  |Skype for Business Server Annuncio conferenza servizio  |5073  |TCP  |Utilizzato per le richieste SIP in arrivo per il servizio Skype for Business Server Annuncio conferenza ,ovvero per le conferenze telefoniche con accesso esterno.  |
|Front End Server  |Skype for Business Server Servizio Parcheggio di chiamata  |5075  |TCP  |Utilizzata per le richieste SIP in arrivo per l'applicazione Parcheggio di chiamata.  |
|Front End Server  |Skype for Business Server Servizio test audio  |5076  |TCP  |Utilizzata per le richieste SIP in arrivo per il servizio Test audio.  |
|Front End Server  |Non applicabile  |5066  |TCP  |Utilizzata per il gateway Enhanced 9-1-1 (E9-1-1) in uscita.  |
|Front End Server  |Skype for Business Server Servizio Response Group  |5071  |TCP  |Utilizzata per le richieste SIP in arrivo per l'applicazione Response Group.  |
|Front End Server  |Skype for Business Server Servizio Response Group  |8404  |TCP (MTLS)  |Utilizzata per le richieste SIP in arrivo per l'applicazione Response Group.  |
|Front End Server  |Skype for Business Server Servizio criteri larghezza di banda  |5080  |TCP  |Utilizzata per il controllo di ammissione di chiamata eseguito dal servizio criteri larghezza di banda per il traffico A/V Edge TURN.  |
|Front End Server  |Skype for Business Server Accesso al server di condivisione file  |445   |SMB/TCP  | Utilizzato per recuperare la Rubrica, il contenuto delle riunioni e altri elementi archiviati nel server condivisione file.  |
|Front End Server  |Skype for Business Server Servizio criteri larghezza di banda  |448  |TCP  |Utilizzato per il controllo di ammissione di chiamata dal Skype for Business Server servizio Criteri di larghezza di banda.  |
|Front End Server in cui risiede l'archivio di gestione centrale  | Skype for Business Server Servizio Agente replica master |445  |TCP  |Utilizzato per eseguire il push dei dati di configurazione dall'archivio di gestione centrale ai server che eseguono Skype for Business Server.  |
|Tutti i server  |SQL Browser  |1434  |UDP  |SQL Browser per la copia replicata locale dei dati dell'archivio di gestione centrale nell'istanza SQL Server locale  |
|Tutti i server interni  |Vari  |49152-57500  |TCP/UDP  |Intervallo di porte multimediali utilizzato per le conferenze audio su tutti i server interni. Utilizzato da tutti i server che terminano l'audio: Front End Server (per il servizio Skype for Business Server Operatore conferenza, il servizio Skype for Business Server Annuncio conferenza e Skype for Business Server Audio/Video Conferencing) e Mediation Server.  |
|Office Server Web Apps  ||443  ||Usato da Skype for Business Server per connettersi al Office Web Apps Server.  |
|Director  |Skype for Business Server Front-End servizio  |5060  |TCP  |Utilizzata facoltativamente per le route statiche ai servizi trusted, come i server di controllo delle chiamate remote.  |
|Director  |Skype for Business Server Front-End servizio  |444  |HTTPS  <br/> TCP  |Comunicazioni interne ai server tra Front End e Director. Inoltre, il certificato client pubblica (nei Front End Server) o verifica se il certificato client è già stato pubblicato.  |
|Director  |Skype for Business Server Servizio Compatibilità Web  |80  |TCP  |Utilizzata per le comunicazioni iniziali dai Director ai nomi di dominio completo (FQDN) della Web farm (gli URL utilizzati dai componenti Web IIS). Durante il normale funzionamento, viene effettuato il passaggio al traffico HTTPS mediante la porta 443 e il tipo di protocollo TCP.  |
|Director  |Skype for Business Server Servizio Compatibilità Web  |443  |HTTPS  |Utilizzata per le comunicazioni dai Director ai nomi di dominio completi (FQDN) della Web farm (gli URL utilizzati dai componenti Web IIS).  |
|Director  |Skype for Business Server Front-End servizio  |5061  |TCP  |Utilizzata per le comunicazioni interne tra i server e per le connessioni client.  |
|Mediation Server  |Skype for Business Server Mediation Service  |5070  |TCP  |Utilizzata dal Mediation Server per le richieste in arrivo dal Front End Server.  |
|Mediation Server  |Skype for Business Server Mediation Service  |5067  |TCP (TLS)  |Utilizzata per le richieste SIP in arrivo dal gateway PSTN.  |
|Mediation Server  |Skype for Business Server Mediation Service  |5068  |TCP  |Utilizzata per le richieste SIP in arrivo dal gateway PSTN.  |
|Mediation Server  |Skype for Business Server Mediation Service  |5070  |TCP (MTLS)  |Utilizzata per le richieste SIP dai Front End Server.  |
|Front End Server della chat persistente  |Persistent Chat SIP  |5041  |TCP (MTLS)  ||
|Front End Server della chat persistente  |Persistent Chat Windows Communication Foundation (WCF)  |881  |TCP (TLS) e TCP (MTLS)  ||
|Front End Server della chat persistente  |Servizio di trasferimento file di Chat persistente  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Alcuni scenari di controllo delle chiamate remote richiedono una connessione TCP tra il Front End Server o Director e il sistema PBX. Anche se Skype for Business Server non utilizza più la porta TCP 5060, durante la distribuzione del controllo delle chiamate remote viene creata una configurazione server attendibile, che associa il nome di dominio completo del server RCC alla porta TCP che verrà utilizzata dal Front End Server o dal Director per connettersi al sistema PBX. Per informazioni dettagliate, vedere il cmdlet **CsTrustedApplicationComputer** nella documentazione Skype for Business Server Management Shell.
  
Per i pool che utilizzano solo il servizio di bilanciamento del carico hardware (non il servizio di bilanciamento del carico DNS), la tabella che segue mostra le porte che devono aprire i servizi di bilanciamento del carico hardware.
  
**Porte del servizio di bilanciamento del carico hardware se si utilizza solo questo servizio di bilanciamento**

|Servizio di bilanciamento del carico|Porta|Protocollo|
|:-----|:-----|:-----|
|Servizio di bilanciamento del carico Front End Server  |5061  |TCP (TLS)  |
|Servizio di bilanciamento del carico Front End Server  |444  |HTTPS  |
|Servizio di bilanciamento del carico Front End Server  |135  |DCOM ed RPC (Remote Procedure Call)  |
|Servizio di bilanciamento del carico Front End Server  |80  |HTTP  |
|Servizio di bilanciamento del carico Front End Server  |8080  |TCP - Recupero di client e dispositivi del certificato radice dal Front End Server - client e dispositivi autenticati da NTLM  |
|Servizio di bilanciamento del carico Front End Server  |443  |HTTPS  |
|Servizio di bilanciamento del carico Front End Server  |4443  |HTTPS (da proxy inverso)  |
|Servizio di bilanciamento del carico Front End Server  |5072  |TCP  |
|Servizio di bilanciamento del carico Front End Server  |5073  |TCP  |
|Servizio di bilanciamento del carico Front End Server  |5075  |TCP  |
|Servizio di bilanciamento del carico Front End Server  |5076  |TCP  |
|Servizio di bilanciamento del carico Front End Server  |5071  |TCP  |
|Servizio di bilanciamento del carico Front End Server  |5080  |TCP  |
|Servizio di bilanciamento del carico Front End Server  |448  |TCP  |
|Servizio di bilanciamento del carico mediation server  |5070  |TCP  |
|Servizio di bilanciamento del carico di Front End Server (se il pool esegue anche Mediation Server)  |5070  |TCP  |
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
|Servizio di bilanciamento del carico Front End Server  |8080  |TCP - Recupero di client e dispositivi del certificato radice dal Front End Server - client e dispositivi autenticati da NTLM  |
|Servizio di bilanciamento del carico Front End Server  |4443  |HTTPS (da proxy inverso)  |
|Servizio di bilanciamento del carico Director  |443  |HTTPS  |
|Servizio di bilanciamento del carico Director  |4443  |HTTPS (da proxy inverso)  |

**Porte client richieste**

|Componente|Porta|Protocollo|Note|
|:-----|:-----|:-----|:-----|
|Client  |67/68  |DHCP  |Utilizzato da Skype for Business Server per trovare il nome di dominio completo della funzione di registrazione, ovvero se DNS SRV ha esito negativo e le impostazioni manuali non sono configurate.  |
|Client  |443  |TCP (TLS)  |Utilizzata per il traffico SIP da client a server per l'accesso utente esterno.  |
|Client  |443  |TCP (PSOM/TLS)  |Utilizzata per l'accesso utente esterno alle sessioni di Web Conferencing.  |
|Client  |443  |TCP (STUN/MSTURN)  |Utilizzata per l'accesso utente esterno alle sessioni A/V e ai supporti multimediali (TCP)  |
|Client  |3478  |UDP (STUN/MSTURN)  |Utilizzato per l'accesso degli utenti esterni alle sessioni A/V e ai supporti (UDP)  |
|Client  |5061  |TCP (MTLS)  |Utilizzata per il traffico SIP da client a server per l'accesso utente esterno.  |
|Client  |6891-6901  |TCP  |Utilizzato per il trasferimento di file tra Skype for Business client e client precedenti.  |
|Client  |1024-65535 \*  |TCP/UDP  |Intervallo di porte audio (almeno 20 porte richieste)  |
|Client  |1024-65535 \*  |TCP/UDP  |Intervallo di porte video (almeno 20 porte richieste).  |
|Client  |1024-65535 \*  |TCP  |Trasferimento file peer-to-peer (per il trasferimento dei file del servizio di conferenza, i client utilizzano PSOM).  |
|Client  |1024-65535 \*  |TCP  |Condivisione applicazioni.  |
|Telefono di area comune Aastra 6721ip  <br/> Telefono da tavolo Aastra 6725ip  <br/> Telefono IP HP 4110 (telefono di area comune)  <br/> Telefono IP HP 4120 (telefono da tavolo)  <br/> Telefono di area comune IP Polycom CX500  <br/> Telefono da tavolo IP Polycom CX600  <br/> Telefono da tavolo IP Polycom CX700  <br/> Telefono IP per conferenze Polycom CX3000  |67/68  |DHCP  |Usato dai dispositivi elencati per trovare il certificato Skype for Business Server, il nome di dominio completo di provisioning e il nome di dominio completo della funzione di registrazione.  |
   
\* Per configurare porte specifiche per questi tipi di supporti, utilizzare il cmdlet CsConferencingConfiguration (parametri ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange).
  
> [!NOTE]
> I programmi di installazione Skype for Business client creano automaticamente le eccezioni del firewall del sistema operativo necessarie nel computer client. 

> [!NOTE]
> Le porte utilizzate per l'accesso degli utenti esterni sono necessarie per qualsiasi scenario in cui il client deve attraversare il firewall dell'organizzazione (ad esempio, eventuali comunicazioni esterne o riunioni ospitate da altre organizzazioni). 
  
## <a name="ipsec-exceptions"></a>Eccezioni IPsec

Per le reti aziendali in cui è stato distribuito Internet Protocol Security (IPsec) (vedere IETF RFC 4301-4309), IPsec deve essere disabilitato nell'intervallo di porte utilizzate per la distribuzione di audio, video e video panoramici. Questa richiesta nasce dall'esigenza di evitare ritardi nell'allocazione delle porte multimediali a causa della negoziazione IPsec.
  
Nella tabella riportata di seguito vengono illustrate le impostazioni di eccezione IPsec consigliate. 
  
**Eccezioni IPsec consigliate**

|Nome regola|IP origine|IP destinazione|Protocollo|Porta origine|Porta destinazione|Requisito di autenticazione|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|A/V Edge Server in ingresso interno  |Qualsiasi  |A/V Edge Server interno  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|A/V Edge Server in ingresso esterno  |Qualsiasi  |A/V Edge Server esterno  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|A/V Edge Server interno in uscita  |A/V Edge Server interno  |Qualsiasi  |UDP &amp; TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|A/V Edge Server esterno in uscita  |A/V Edge Server esterno  |Qualsiasi  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Mediation Server in ingresso  |Qualsiasi  |Mediation  <br/> Server  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Mediation Server in uscita  |Mediation  <br/> Server  |Qualsiasi  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Operatore Conferenza in ingresso  |Qualsiasi  |Front End Server con Operatore Conferenza  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Operatore Conferenza in uscita  |Front End Server con Operatore Conferenza  |Qualsiasi  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|A/V Conferencing Server in ingresso  |Qualsiasi  |Front End Server  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|A/V Conferencing in uscita  |Front End Server  |Qualsiasi  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Exchange in ingresso  |Qualsiasi  |Messaggistica unificata di Exchange  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Server di condivisione applicazioni in ingresso  |Qualsiasi  |Server di condivisione applicazioni  |TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Server di condivisione applicazioni in uscita  |Server di condivisione applicazioni  |Qualsiasi  |TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Exchange in uscita  |Messaggistica unificata di Exchange  |Qualsiasi  |UDP e TCP  |Qualsiasi  |Qualsiasi  |Non autenticare  |
|Client  |Qualsiasi  |Qualsiasi  |UDP  |Intervallo porte multimediali specificato  |Qualsiasi  |Non autenticare  |