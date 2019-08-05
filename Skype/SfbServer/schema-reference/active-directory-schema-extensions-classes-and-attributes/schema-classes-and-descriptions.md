---
title: Classi e descrizioni dello schema in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: Questa sezione descrive tutte le classi dello schema usate da Skype for Business Server.
ms.openlocfilehash: 6d27ff464bcd4613f12180b8f263686c9cc04bcd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194856"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Classi e descrizioni dello schema in Skype for Business Server
 
Questa sezione descrive tutte le classi dello schema usate da Skype for Business Server. 
  
## <a name="schema-classes-and-descriptions"></a>Classi e descrizioni dello schema

|**Classe**|**Descrizione**|**Commenti**|
|:-----|:-----|:-----|
|Destinatario della posta elettronica  <br/> |Destinatario della messaggistica unificata di Exchange.  <br/> |Questa classe ausiliaria viene condivisa con la messaggistica unificata di Exchange.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |Questa classe è un contenitore per più contatti dell'applicazione e non contiene alcun attributo.  <br/> |Novità di Microsoft Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |Questa classe contiene la voce per il punto di controllo del servizio per un'istanza di Unified Communications Application Services (UCAS).  <br/> |Nuovo in Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |Questa classe fornisce un'associazione da un pool specifico al relativo servizio applicazione.  <br/> |Nuovo in Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |Questa classe ausiliaria di msRTCSIP-ApplicationServer contiene gli attributi che rappresentano le impostazioni per le istanze del servizio applicazione.  <br/> |Nuovo in Communications Server 2007 R2.  <br/> |
|msRTCSIP-Archive (obsoleto)  <br/> |Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene tutte le impostazioni correlate all'archiviazione.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-ArchivingServer (obsoleto)  <br/> |Questa classe rappresenta un singolo server di archiviazione di messaggistica istantanea. Un'istanza di questa classe viene creata quando un computer viene attivato come server di archiviazione di messaggistica istantanea, ad esempio un computer in cui è installato il servizio di archiviazione di messaggistica istantanea.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |Questa classe è un contenitore per più istanze di directory conferenza e non contiene alcun attributo.  <br/> |Nuovo in Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |Questa classe contiene gli attributi che rappresentano le impostazioni per una specifica directory conferenza.  <br/> |Nuovo in Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |SCP (Generic Service Control Point) per specificare il computer come server che usa Skype for Business Server.  <br/> |Nuovo in Lync 2010.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |Questa classe ausiliaria contiene le impostazioni per una banca di Skype for Business Web App.  <br/> |Nuovo in Communications Server 2007 R2.  <br/> |
|msRTCSIP-Domain  <br/> |Questa classe contiene gli attributi che definiscono i domini configurati del registrar SIP.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |Questo contenitore di classi rappresenta un singolo servizio Edge di Access. Poiché un servizio di Access Edge viene distribuito nella rete perimetrale e i clienti in genere non consentono l'accesso a servizi di dominio Active Directory dalla rete perimetrale, le istanze del servizio Access Edge non vengono unite alla rete Active Directory della Intranet. Di conseguenza, i proxy di Access non vengono registrati automaticamente in servizi di dominio Active Directory. L'amministratore deve configurare manualmente l'esistenza di ogni istanza di Access Edge Services in servizi di dominio Active Directory.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |Questa classe ausiliaria per msRTCSIP-MCU contiene gli attributi che rappresentano le impostazioni per i server di conferenza.  <br/> |Novità di Microsoft Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |Questa classe ausiliaria di msRTCSIP-MediationServer contiene gli attributi che rappresentano le impostazioni per i server di mediazione.  <br/> |Nuovo in Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |Questa classe ausiliaria di msRTCSIP-Server contiene gli attributi che rappresentano le impostazioni per i server SIP.  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene tutte le impostazioni correlate alla Federazione.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |Questa classe contiene tutte le impostazioni che si applicano in una distribuzione di Skype for Business Server.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (obsoleto)  <br/> |Questa classe rappresenta un singolo criterio di riunione di Office Communications Server.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |Oggetto impostazione topologia globale locale.  <br/> |Nuovo in Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |Contenitore per contenere gli oggetti di impostazione della topologia globale.  <br/> |Nuovo in Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |Questa classe è un contenitore che rappresenta un'istanza di una regola di normalizzazione della posizione.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |Questa classe viene creata dall'applicazione per i servizi di conferenza e contiene gli attributi usati per categorizzare i numeri di telefono per le conferenze per area geografica.  <br/> |Nuovo in Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |Questa classe è un contenitore per più istanze di mapping dei contatti di posizione e non contiene alcun attributo.  <br/> |Nuovo in Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationProfile  <br/> |Questa classe è un contenitore che rappresenta un profilo di posizione specifico.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (obsoleto)  <br/> |Questa classe è un contenitore per più profili di posizione e non contiene alcun attributo.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalizations (obsoleto)  <br/> |Questa classe è un contenitore per più regole di normalizzazione locali e non contiene alcun attributo.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-MCU  <br/> |Questa classe rappresenta un singolo server di conferenza.  <br/> |Nuovo in Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactories  <br/> |Questa classe contiene più classi msRTCSIP-MCUFactory e non ha attributi.  <br/> |Nuovo in Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactory  <br/> |Questa classe è un contenitore che rappresenta una factory di servizi di conferenza per un singolo tipo di supporto. Viene creata un'istanza di questa classe quando viene attivato il primo server di conferenza per il tipo specifico e il fornitore.  <br/> |Nuovo in Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |Questa classe fornisce un'associazione da un pool specifico alla propria factory di server di conferenza.  <br/> |Nuovo in Communications Server 2007.  <br/> |
|msRTCSIP-MediationServer  <br/> |Questa classe contiene la voce per il punto di controllo del servizio di un Mediation Server.  <br/> |Nuovo in Communications Server 2007.  <br/> |
|msRTCSIP-Meeting (obsoleto)  <br/> |Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi che rappresentano le impostazioni delle riunioni configurabili.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-Mobility  <br/> |Contenitore che archivia le impostazioni di mobilità globale.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |Questa classe contiene gli attributi che rappresentano le impostazioni per un singolo server di monitoraggio.  <br/> |Nuovo in Communications Server 2007 R2.  <br/> |
|msRTCSIP-PhoneRoute (obsoleto)  <br/> |Questa classe è un contenitore che rappresenta un'istanza di una route con costi minimi a un gateway o un set di gateway. Queste informazioni vengono usate da tutti i pool o i server aziendali che usano Standard Edition per instradare le chiamate in uscita alla rete PSTN (Public Switched Telephone Network) in modo più conveniente.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-PhoneRoutes (obsoleto)  <br/> |Questa classe è un contenitore per più route di costo inferiore e non contiene alcun attributo.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-Policy (obsolete)  <br/> |Questa classe contiene più classi di criteri di Lync Server e non ha alcun attributo.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-Pool  <br/> |Questa classe rappresenta un singolo pool di Skype for Business Server.  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |Questa classe contiene più pool di Skype for Business Server e non ha alcun attributo.  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |Questa classe rappresenta il punto di controllo pointservice del controllo del servizio di un pool. Gli utenti ospitati in un pool hanno il punto di attributo msRTCSIP-PrimaryHomeServer su un'istanza della classe.  <br/> |-  <br/> |
|msRTCSIP-Presence  <br/> |Contenitore in cui sono archiviate le impostazioni di presenza globale.  <br/> |-  <br/> |
|msRTCSIP-Registrar  <br/> |Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi che rappresentano le impostazioni utente gestite dai server di registrazione SIP.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (obsoleto)  <br/> |Questa classe è un contenitore che rappresenta un'istanza dell'utilizzo di una route telefonica. La classe di utilizzo di una route telefonica è costituita da un campo attributo e da un campo Description. Il campo attributo definisce un tipo di utilizzo. Il campo Description consente agli amministratori di descrivere l'utilizzo di questo attributo nell'itinerario telefonico.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-RouteUsages (obsoleto)  <br/> |Questa classe contiene più istanze della classe msRTCSIP-RouteUsage e non ha alcun attributo.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-search  <br/> |Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi che limitano e controllano l'ambito dei risultati della ricerca.  <br/> |-  <br/> |
|msRTCSIP-Server  <br/> |Questa classe rappresenta un singolo server che utilizza Skype for Business Server.  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |Questa classe contiene il contenitore di impostazioni globali e gli oggetti msRTCSIP-Domain.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |Questa classe contiene gli attributi che rappresentano le impostazioni per un server di conferenza attendibile.  <br/> |Nuovo in Communications Server 2007.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |Questa classe contiene più istanze della classe msRTCSIP-TrustedMCU e non ha alcun attributo.  <br/> |Nuovo in Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxies  <br/> |Questa classe contiene più classi msRTCSIP-TrustedProxy e non contiene alcun attributo.  <br/> |Nuovo in Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxy  <br/> |Questa classe è un contenitore che rappresenta un server che gestisce il server proxy. Viene creata un'istanza di questa classe quando si attiva un nuovo server proxy in un computer collegato a servizi di dominio Active Directory.  <br/> |Nuovo in Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServer  <br/> |Questa classe contiene gli attributi che rappresentano le impostazioni per un server attendibile.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |Questa classe è un contenitore che rappresenta un servizio attendibile instradabile con un indirizzo GRUU (Globally User Agent URI). Viene creata un'istanza di questa classe quando viene attivato un nuovo server considerato attendibile da Skype for Business Server. Questo server attendibile deve essere associato a un dominio Active Directory.  <br/> |Nuovo in Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServices  <br/> |Questa classe è un contenitore per più server GRUU e non contiene alcun attributo.  <br/> |Nuovo in Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |Questa classe contiene gli attributi che rappresentano le impostazioni per un componente Web attendibile.  <br/> |Nuovo in Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |Questa classe contiene più istanze della classe msRTCSIP-TrustedWebComponentServer e non ha alcun attributo.  <br/> |Nuovo in Communications Server 2007.  <br/> |
|msRTCSIP-UnifiedCommunications (obsoleto)  <br/> |Questa classe ausiliaria di msRTCSIP-GlobalContainer contiene gli attributi correlati alle comunicazioni unificate.  <br/> |Obsoleto in Lync Server 2010.  <br/> |
|msRTCSIP-WebComponents  <br/> |Questa classe contiene il punto di controllo del controllo del servizio pointservice per Internet Information Server (IIS). Identifica un server come server di componenti Web.  <br/> |Nuovo in Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |Questa classe fornisce un'associazione da un pool specifico ai componenti Web che verranno usati dal pool.  <br/> |Nuovo in Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Questa classe ausiliaria di msRTCSIP-WebComponents contiene gli attributi che rappresentano le impostazioni per i componenti Web.  <br/> |Nuovo in Communications Server 2007.  <br/> |
   

