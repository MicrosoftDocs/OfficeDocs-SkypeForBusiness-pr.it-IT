---
title: Classi e descrizioni dello schema in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: In questa sezione vengono descritte tutte le classi dello schema utilizzate da Skype for Business Server .
ms.openlocfilehash: ec9c4a7612455df6d004289f88ccdb7efb3d6334
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596440"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Classi e descrizioni dello schema in Skype for Business Server
 
In questa sezione vengono descritte tutte le classi dello schema utilizzate da Skype for Business Server . 
  
## <a name="schema-classes-and-descriptions"></a>Classi e descrizioni di schemi

|**Classe**|**Descrizione**|**Comments**|
|:-----|:-----|:-----|
|Mail-Recipient  <br/> |Exchange Destinatario di posta elettronica di messaggistica unificata.  <br/> |Questa classe ausiliaria è condivisa con la Exchange messaggistica unificata.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |Questa classe è un contenitore per più contatti applicazione e non include alcun attributo.  <br/> |Novità di Microsoft Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |Questa classe contiene la voce relativa al punto di controllo del servizio per un'istanza dei servizi per applicazioni per comunicazioni unificate  <br/> |Novità di Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |Questa classe fornisce un'associazione da un pool specifico al relativo servizio applicazione.  <br/> |Novità di Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |Questa classe ausiliaria di msRTCSIP-ApplicationServer contiene attributi che rappresentano le impostazioni per le istanze del servizio applicazione.  <br/> |Novità di Communications Server 2007 R2.  <br/> |
|msRTCSIP-Archive (obsoleta)  <br/> |Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene tutte le impostazioni relative all'archiviazione.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-ArchivingServer (obsoleta)  <br/> |Questa classe rappresenta un singolo server di archiviazione della messaggistica istantanea. Viene creata un'istanza di questa classe quando un computer viene attivato come server di archiviazione della messaggistica istantanea, come nel caso di un computer in cui è installato il servizio di archiviazione della messaggistica istantanea.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |Questa classe è un contenitore per più istanze di directory conferenze e non include alcun attributo.  <br/> |Novità di Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |Questa classe contiene gli attributi che rappresentano le impostazioni per una directory conferenze specifica.  <br/> |Novità di Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |Punto di controllo del servizio generico (SCP) per specificare il computer come server che esegue Skype for Business Server.  <br/> |Novità di Lync 2010.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |Questa classe ausiliaria contiene le impostazioni per un Skype for Business Web App bancario.  <br/> |Novità di Communications Server 2007 R2.  <br/> |
|msRTCSIP-Domain  <br/> |Questa classe contiene gli attributi che definiscono i domini configurati della funzione di registrazione SIP.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |Questo contenitore di classe rappresenta un singolo servizio Access Edge. Poiché nella rete perimetrale viene distribuito un servizio Access Edge e i clienti in genere non consentono l'accesso a Servizi di dominio Active Directory dalla rete perimetrale, le istanze del servizio Access Edge non vengono unite alla rete Active Directory della intranet. I proxy di accesso non vengono pertanto registrati automaticamente in Servizi di dominio Active Directory. L'amministratore deve configurare manualmente l'esistenza di ogni istanza del servizio Access Edge in Servizi di dominio Active Directory.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |Questa classe ausiliaria di msRTCSIP-MCU contiene gli attributi che rappresentano le impostazioni per i server per conferenze.  <br/> |Novità di Microsoft Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |Questa classe ausiliaria di msRTCSIP-MediationServer contiene gli attributi che rappresentano le impostazioni per i server Mediation Server.  <br/> |Novità di Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |Questa classe ausiliaria di msRTCSIP-Server contiene gli attributi che rappresentano le impostazioni per i server SIP.  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene tutte le impostazioni relative alla federazione.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |Questa classe contiene tutte le impostazioni che si applicano in una Skype for Business Server distribuzione.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (obsoleta)  <br/> |Questa classe rappresenta un singolo criterio Office riunione di Communications Server.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |Oggetto impostazione della topologia globale locale.  <br/> |Novità di Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |Contenitore di oggetti impostazione della topologia globale.  <br/> |Novità di Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |Questa classe è un contenitore che rappresenta un'istanza di una regola di normalizzazione della località.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |Questa classe viene creata dall'applicazione Operatore conferenza e contiene gli attributi utilizzati per categorizzare i numeri di telefono delle conferenze per area geografica.  <br/> |Novità di Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |Questa classe è un contenitore per più istanze di mapping dei contatti località e non include alcun attributo.  <br/> |Novità di Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationProfile  <br/> |Questa classe è un contenitore che rappresenta un profilo località specifico.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (obsoleta)  <br/> |Questa classe è un contenitore per più profili località e non include alcun attributo.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalizations (obsoleta)  <br/> |Questa classe è un contenitore per più regole di normalizzazione locale e non include alcun attributo.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-MCU  <br/> |Questa classe rappresenta un singolo server per conferenze.  <br/> |Novità di Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactories  <br/> |Questa classe contiene più classi msRTCSIP-MCUFactory e non include alcun attributo.  <br/> |Novità di Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactory  <br/> |Questa classe è un contenitore che rappresenta un componente Conferencing Server Factory per un singolo tipo di supporto. Viene creata un'istanza di questa classe quando viene attivato il primo server per conferenze per questo tipo e questo fornitore specifici.  <br/> |Novità di Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |Questa classe fornisce un'associazione tra un pool specifico e il relativo componente Conferencing Server Factory.  <br/> |Novità di Communications Server 2007.  <br/> |
|msRTCSIP-MediationServer  <br/> |Questa classe contiene la voce relativa al punto di controllo del servizio di Mediation Server.  <br/> |Novità di Communications Server 2007.  <br/> |
|msRTCSIP-Meeting (obsoleta)  <br/> |Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi che rappresentano le impostazioni configurabili per le riunioni.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-Mobility  <br/> |Contenitore in cui vengono archiviate le impostazioni per dispositivi mobili globali.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |Questa classe contiene attributi che rappresentano le impostazioni per un singolo Monitoring Server.  <br/> |Novità di Communications Server 2007 R2.  <br/> |
|msRTCSIP-PhoneRoute (obsoleta)  <br/> |Questa classe è un contenitore che rappresenta un'istanza di Least Cost Routing a un gateway o un insieme di gateway. Queste informazioni vengono utilizzate da tutti i pool o Server Enterprise che eseguono la versione Standard Edition per instradare le chiamate in uscita alla rete PSTN nel modo più economico possibile.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-PhoneRoutes (obsoleta)  <br/> |Questa classe è un contenitore per più istanze di Least Cost Routing e non include alcun attributo.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-Policies (obsoleta)  <br/> |Questa classe contiene più classi di criteri di Lync Server e non dispone di alcun attributo.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-Pool  <br/> |Questa classe rappresenta un singolo Skype for Business Server pool.  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |Questa classe contiene più Skype for Business Server pool e non dispone di alcun attributo.  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |Questa classe rappresenta il punto di controllo del servizio di un pool. L'attributo msRTCSIP-PrimaryHomeServer degli utenti ospitati in un pool punta a un'istanza di questa classe.  <br/> |-  <br/> |
|msRTCSIP-Presence  <br/> |Contenitore in cui vengono archiviate le impostazioni presenza globali.  <br/> |-  <br/> |
|msRTCSIP-Registrar  <br/> |Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi che rappresentano le impostazioni utente gestite dai server di registrazione SIP.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (obsoleta)  <br/> |Questa classe è un contenitore che rappresenta un'istanza di un utilizzo di route telefonica. Una classe utilizzo di route telefonica è costituita da un campo attributo e da un campo descrizione. Il campo attributo definisce un tipo di utilizzo. Il campo descrizione consente agli amministratori di descrivere l'utilizzo di questo attributo nella route telefonica.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-RouteUsages (obsoleta)  <br/> |Questa classe contiene più istanze della classe msRTCSIP-RouteUsage e non include alcun attributo.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-Search  <br/> |Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi che limitano e controllano l'ambito dei risultati della ricerca.  <br/> |-  <br/> |
|msRTCSIP-Server  <br/> |Questa classe rappresenta un singolo server che esegue Skype for Business Server.  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |Questa classe contiene il contenitore delle impostazioni globali e gli oggetti msRTCSIP-Domain.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |Questa classe contiene gli attributi che rappresentano le impostazioni per un server per conferenze trusted.  <br/> |Novità di Communications Server 2007.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |Questa classe contiene più istanze della classe msRTCSIP-TrustedMCU e non include alcun attributo.  <br/> |Novità di Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxies  <br/> |Questa classe contiene più classi msRTCSIP-TrustedProxy e non include alcun attributo.  <br/> |Novità di Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxy  <br/> |Questa classe è un contenitore che rappresenta un server che esegue un server proxy. Viene creata un'istanza di questa classe quando si attiva un nuovo server proxy in un computer che fa parte di Servizi di dominio Active Directory.  <br/> |Novità di Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServer  <br/> |Questa classe contiene gli attributi che rappresentano le impostazioni per un server trusted.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |Questa classe è un contenitore che rappresenta un servizio trusted instradabile utilizzando un indirizzo GRUU (Globally Routable User Agent URI). Un'istanza di questa classe viene creata quando viene attivato un nuovo server Skype for Business Server attendibile. Il server trusted deve fare parte del dominio di Active Directory.  <br/> |Novità di Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServices  <br/> |Questa classe è un contenitore per più server GRUU e non include alcun attributo.  <br/> |Novità di Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |Questa classe contiene gli attributi che rappresentano le impostazioni per un server Web Components Server trusted.  <br/> |Novità di Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |Questa classe contiene più istanze della classe msRTCSIP-TrustedWebComponentServer e non include alcun attributo.  <br/> |Novità di Communications Server 2007.  <br/> |
|msRTCSIP-UnifiedCommunications (obsoleta)  <br/> |Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi relativi alle comunicazioni unificate.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-WebComponents  <br/> |Questa classe contiene il punto di controllo del servizio di IIS (Internet Information Server) e identifica un server come Web Components Server.  <br/> |Novità di Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |Questa classe fornisce un'associazione tra un pool specifico e i componenti Web che verranno utilizzati dal pool.  <br/> |Novità di Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Questa classe ausiliaria di msRTCSIP-WebComponents contiene gli attributi che rappresentano le impostazioni per i componenti Web.  <br/> |Novità di Communications Server 2007.  <br/> |
   

