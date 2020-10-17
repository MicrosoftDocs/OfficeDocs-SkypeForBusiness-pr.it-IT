---
title: 'Lync Server 2013: visualizzazione dello stato delle impostazioni globali per una foresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7922fe79d97a1fa83fdaa5afbc1eeddee8523e37
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535583"
---
# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>Visualizzazione dello stato delle impostazioni globali per una foresta in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-20_

Gli amministratori devono esaminare mensilmente le impostazioni globali per una distribuzione di Lync Server 2013. L'obiettivo è quello di esaminare le impostazioni implementate in base a un insieme di configurazioni note, ovvero una configurazione di base per garantire che le impostazioni siano valide e per determinare se la documentazione di base deve essere aggiornata. Le modifiche apportate all'impostazione globale devono essere implementate tramite un processo di controllo delle modifiche che dovrebbe includere la documentazione delle nuove impostazioni.

Le impostazioni globali che devono essere rivedute sono descritte nelle sezioni seguenti:

<div>

## <a name="check-general-settings"></a>Controllare le impostazioni generali

Controllare le impostazioni generali, inclusi i domini SIP (Session Initiation Protocol) per Lync Server 2013.

È possibile restituire le informazioni sul dominio SIP utilizzando Windows PowerShell e il cmdlet **Get-CsSipDomain** . Per restituire queste informazioni, eseguire il `Get-CsSipDomain` comando di Windows PowerShell.

Get-CsSipDomain restituirà informazioni simili a quelle per tutti i domini SIP autorizzati:

Nome dell'identità predefinito

\-------- ---- ---------

fabrikam.com fabrikam.com true

na.fabrikam.com na.fabrikam.com false

Se la proprietà IsDefault è impostata su true, il dominio corrispondente è il dominio SIP predefinito. È possibile utilizzare il cmdlet Set-CsSipDomain per modificare il dominio SIP predefinito per l'organizzazione. Tuttavia, non è possibile eliminare solo il dominio SIP predefinito, perché ciò non comporta un dominio predefinito. Se si desidera eliminare il dominio fabrikam.com (come illustrato nell'esempio precedente), è necessario prima di tutto configurare na.fabrikam.com in modo che sia il dominio predefinito.

</div>

<div>

## <a name="check-meeting-settings"></a>Controllare le impostazioni di riunione

Le impostazioni delle riunioni includono le definizioni dei criteri di riunione e il supporto per la partecipazione degli utenti anonimi alle riunioni.

È possibile recuperare le impostazioni di configurazione delle riunioni utilizzando Windows PowerShell e il cmdlet **Get-CsMeetingConfiguration** . Ad esempio, questo comando restituisce le informazioni sulle impostazioni di configurazione della riunione globale:

Get-CsMeetingConfiguration-Identity "Global" le impostazioni di configurazione delle riunioni possono essere configurate anche nell'ambito del sito. Per questo motivo, è possibile utilizzare il comando seguente, che restituisce informazioni su tutte le impostazioni di configurazione delle riunioni:

`Get-CsMeetingConfiguration`

Il cmdlet **Get-CsMeetingConfiguration** restituisce informazioni simili alle seguenti:

Identità: globale

PstnCallersBypassLobby: true

EnableAssignedConferenceType: true

DesignateAsPresenter: società

AssignedConferenceTypeByDefault: true

AdmitAnonymousUsersByDefault: true

Anche in questo caso, l'elemento finale nell'elenco, **AdmitAnonymousUsersByDefault**, consente di abilitare o disabilitare la capacità degli utenti anonimi di partecipare alle riunioni.

Quando si verificano le impostazioni di configurazione delle riunioni, potrebbe essere utile confrontare le impostazioni correnti con gli equivalenti predefiniti. È possibile visualizzare le impostazioni di configurazione delle riunioni predefinite eseguendo il comando riportato di seguito:

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

Il comando precedente consente di creare un'istanza solo in memoria delle impostazioni di configurazione della riunione globale, un'istanza che utilizza il valore predefinito per ogni proprietà. Quando si esegue il comando, non vengono create impostazioni di configurazione delle riunioni effettive. Tuttavia, tutti i valori della proprietà predefinita verranno visualizzati sullo schermo.

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>Controllare i server perimetrali e le relative impostazioni

È possibile recuperare le informazioni sui server perimetrali utilizzando Windows PowerShell. Questo comando restituisce informazioni su tutti i server perimetrali configurati per l'utilizzo nell'organizzazione:

`Get-CsService -EdgeServer`

Le informazioni restituite includono tutte le impostazioni di FQDN e di porta per ogni server perimetrale:

Identità: EdgeServer: dc.fabrikam.com

Registrar: Registrar: LYNC-SE.fabrikam.com

AccessEdgeInternalSipPort: 5061

AccessEdgeExternalSipPort: 5061

AccessEdgeClientPort: 443

DataPsomServerPort: 8057

DataPsomClientPort: 444

MediaRelayAuthEdgePort: 5062

MediaRelayAuthInternalTurnTcpPort: 443

MediaRelayAuthExternalTurnTcpPort: 445

MediaRelayAuthInternalTurnUdpPort: 3478

MediaRelayAuthExternalTurnUdpPort: 3478

MediaCommunicationPortStart: 50000

MediaComunicationPortCount: 10000

AccessEdgeExternalFqdn: dc.fabrikam.com

DataEdgeExternalFqdn: dc.fabrikam.com

AVEdgeExternalFqdn :

InternalInterfaceFqdn :

ExternalMrasFqdn: dc.fabrikam.com

DependentServiceList: {Registrar: LYNC-SE.fabrikam.com,

ConferencingServer: LYNC-SE. fabrikam

com, MediationServer: LYNC-SE.

fabrikam.com}

ServiceId: fabrikam.com-EdgeServer-2

SiteId: site: fabrikam. com

PoolFqdn: dc.fabrikam.com

Versione: 5

Ruolo: EdgeServer

<div>

## <a name="check-federation-settings"></a>Controllare le impostazioni di Federazione

Verificare le impostazioni di federazione, ad esempio se sono configurate e, se la risposta è "Sì", il nome di dominio completo e la porta. La Federazione è abilitata e disabilitata utilizzando la raccolta globale delle impostazioni di configurazione di Access Edge. Tra le altre cose, significa che la Federazione è configurata in base a tutto o niente: la Federazione è abilitata per l'intera organizzazione o la Federazione è disabilitata per l'intera organizzazione.

Le impostazioni di configurazione di Access Edge possono essere restituite tramite Windows PowerShell. A tale scopo, eseguire il comando di Windows PowerShell seguente:

`Get-CsAccessEdgeConfiguration`

In questo modo, il comando restituirà dati simili ai seguenti:

Identità: globale

AllowAnonymousUsers: false

AllowFederatedUsers: false

AllowOutsideUsers: false

BeClearingHouse: false

EnablePartnerDiscovery: false

EnableArchivingDisclaimer: false

KeepCrlsUpToDateForPeers: true

MarkSourceVerifiableOnOutgoingMessages: true

OutgoingTlsCountForFederatedPartners: 4

RoutingMethod: UseDnsSrvRouting

Se la proprietà **AllowFederatedUsers** è impostata su true, significa che la Federazione è abilitata per l'organizzazione. (L'impostazione di **AllowFederatedUsers** su true significa anche che, in uno scenario di dominio diviso, gli utenti locali potranno comunicare senza problemi con gli utenti in-the-cloud).

Per recuperare il nome di dominio completo e le impostazioni della porta per il server perimetrale, vedere l'attività precedente (server perimetrali e relative impostazioni).

L'abilitazione della Federazione nell'ambito globale implica solo che gli utenti possano comunicare con utenti federati. Per determinare se i singoli utenti possono comunicare effettivamente con gli utenti federati, è necessario esaminare i criteri di accesso utente esterno assegnati all'utente.

Le informazioni sull'accesso degli utenti esterni possono essere restituite tramite Windows PowerShell. Ad esempio, questo comando restituisce le informazioni per il criterio di accesso utente esterno globale:

`Get-CsExternalAccessPolicy -Identity "Global"`

E questo comando restituisce informazioni su tutti i criteri di accesso degli utenti esterni:

`Get-CsExternalAccessPolicy`

Le informazioni restituite saranno simili alle seguenti:

Identity: false

Descrizione

EnableFederationAccess: false

EnablePublicCloudAccess: false

EnablePublicCloudAccessAudioVideoAccess: false

EnableOutsideAccess: false

Se **EnableFederationAccess** è impostato su true, gli utenti gestiti dal criterio specificato potranno comunicare con gli utenti federati.

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>Controllare le impostazioni di archiviazione

Controllare le impostazioni di archiviazione per le comunicazioni interne e federate. Prima di verificare le impostazioni per l'archiviazione interna ed esterna, è necessario verificare che l'archiviazione sia abilitata.

È possibile verificare le impostazioni di configurazione dell'archiviazione utilizzando Windows PowerShell e il cmdlet Get-CsArchivingConfiguration:

`Get-CsArchivingConfiguration -Identity "Global"`

Si noti che le impostazioni di archiviazione possono essere configurate anche nell'ambito del sito. Per restituire informazioni su tutte le impostazioni di archiviazione, utilizzare questo comando:

`Get-CsArchivingConfiguration`

Il cmdlet Get-CsArchivingConfiguration restituisce dati simili al seguente:

Identità: globale

EnableArchiving: false

EnablePurging: false

PurgeExportedArchivesOnly: false

BlockOnArchiveFailure: false

KeepArchivingDataForDays: 14

PurgeHourOfDay: 2

ArchiveDuplicateMessages: true

CachePurgingInterval: 24

Se la proprietà EnableArchiving è impostata su false, significa che non verranno archiviate sessioni di comunicazione. Se si desidera archiviare solo le sessioni di messaggistica istantanea, utilizzare un comando simile al seguente per abilitare l'archiviazione delle sessioni di messaggistica istantanea:

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Per archiviare le sessioni di conferenza e le sessioni di messaggistica istantanea, utilizzare questo comando:

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Se si desidera confrontare le impostazioni di archiviazione correnti con quelle predefinite, eseguire il comando di Windows PowerShell seguente:

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

Questo comando consente di creare un'istanza solo in memoria delle impostazioni di configurazione di archiviazione globale. Non si tratta di una vera e propria raccolta di impostazioni utilizzata da Lync Server. Tuttavia, vengono visualizzati i valori predefiniti per tutte le proprietà di configurazione dell'archiviazione.

È inoltre possibile utilizzare questo comando per restituire il nome di dominio completo dei server di archiviazione:

`Get-CsService -ArchivingServer`

Dopo aver verificato che l'archiviazione sia abilitata, è possibile visualizzare i criteri di archiviazione per determinare se le sessioni di comunicazione interne ed esterne vengono archiviate.

Le informazioni sui criteri di archiviazione possono essere recuperate utilizzando il cmdlet Get-CsArchivingPolicy. Ad esempio, questo comando restituisce le informazioni sul criterio di archiviazione globale:

`Get-CsArchivingPolicy -Identity "Global"`

Poiché i criteri di archiviazione possono essere configurati anche nel sito e nell'ambito per utente, è possibile anche utilizzare questo comando, che restituisce informazioni su tutti i criteri di archiviazione:

`Get-CsArchivingPolicy`

Le informazioni ricevute da Get-CsArchivingPolicy saranno simili alle seguenti:

Identità: globale

Descrizione

ArchiveInternal: false

ArchiveExternal: false

Si noti che, per impostazione predefinita, sia l'archiviazione interna sia quella esterna sono disattivate in un criterio di archiviazione.

</div>

<div>

## <a name="check-cdr-settings"></a>Controllare le impostazioni di registrazione dettagli chiamata

Controllare le impostazioni del record dettagli chiamata (CDR) per la registrazione dei dettagli delle chiamate peer-to-peer, conferenze e vocali. Per informazioni dettagliate sulle impostazioni di registrazione dettagli chiamata, è possibile utilizzare il cmdlet **Get-CsCdrConfiguration** . Ad esempio, questo comando restituisce informazioni sulla raccolta globale delle impostazioni di configurazione di registrazione dettagli chiamata:

`Get-CsCdrConfiguration -Identity "Global"`

Poiché CDR può anche essere configurato nell'ambito del sito, è possibile che si desideri eseguire questo comando, che restituisce informazioni su tutte le impostazioni di configurazione di registrazione dettagli chiamata:

`Get-CsCdrConfiguration`

Il cmdlet Get-CsCdrConfiguration restituisce informazioni simili a queste per ogni raccolta di impostazioni di configurazione di registrazione dettagli chiamata:

Identità: globale

EnableCDR: true

EnablePurging: true

KeepCallDetailForDays: 60

KeepErrorReportForDays: 60

PurgeHourOfDay: 2

È possibile restituire informazioni simili per il monitoraggio QoE utilizzando il cmdlet Get-CsQoEConfiguration. Ad esempio, questo comando restituisce informazioni sulla raccolta globale di impostazioni di configurazione QoE:

`Get-QoEConfiguration -Identity "Global"`

Queste informazioni saranno simili alle seguenti:

Identità: globale

ExternalConsumerIssuedCertId :

EnablePurging: true

KeepQoEDataForDays: 60

PurgeHourOfDay: 1

EnableExternalConsumer: false

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE: true

Se si desidera confrontare le impostazioni di registrazione dettagli chiamata correnti con le impostazioni di registrazione dettagli chiamata predefinite, è possibile rivedere i valori predefiniti eseguendo il comando seguente:

`New-CsCdrConfiguration -Identity "Global" -InMemory`

Analogamente, i valori predefiniti per il monitoraggio QoE possono essere recuperati utilizzando il comando seguente:

`New-CsQoEConfiguration -Identity "Global" -InMemory`

È anche possibile restituire il nome di dominio completo dei server di monitoraggio eseguendo il comando riportato di seguito:

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>Controllare le impostazioni vocali

Le impostazioni vocali in genere importanti per gli amministratori sono contenute nei criteri vocali e nelle route vocali: i criteri vocali contengono le impostazioni che determinano le funzionalità esposte ai singoli utenti, ad esempio la possibilità di inoltrare o trasferire le chiamate, mentre le route vocali determinano come (e se) le chiamate vengono instradate attraverso la rete PSTN.

Le informazioni sui criteri vocali possono essere recuperate tramite Windows PowerShell. Ad esempio, questo comando restituisce le informazioni sul criterio vocale globale:

`Get-CsVoicePolicy -Identity "Global"`

Questo comando restituisce informazioni su tutti i criteri vocali configurati per l'utilizzo nell'organizzazione:

`Get-CsVoicePolicy`

Le informazioni restituite dal cmdlet Get-CsVoicePolicy sono analoghe a quelle riportate di seguito:

Identità: globale

PstnUsages {}

Descrizione

AllowSimulRing: true

AllowCallForwarding: true

AllowPSTNReRouting: true

Nome: DefaultPolicy

EnableDelegation: true

EnableTeamCall: true

EnableCallTransfer: true

EnableCallPark: false

EnableMaliciousCallTracing: false

EnableBWPolicyOverride: false

PreventPSTNTollBypass: false

È inoltre possibile creare query che restituiscono un sottoinsieme di criteri vocali. Ad esempio, questo comando restituisce tutti i criteri vocali che consentono l'inoltro di chiamata:

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

Questo comando consente di restituire tutti i criteri vocali che non consentono l'inoltro delle chiamate:

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

In Windows PowerShell, utilizzare il cmdlet Get-CsVoiceRouting per restituire le informazioni sulle route vocali:

`Get-CsVoiceRoute`

Questo comando restituisce informazioni come questa per tutte le route vocali:

Identità: LocalRoute

Priorità: 0

Descrizione

NumberPattern: ^ ( \\ + 1 \[ 0-9 \] {10} ) $

PstnUsages {}

PstnGatewayList {}

Nome: LocalRoute

SuppressCallerId

AlternateCallerId

Lync Server consente di creare route vocali che non dispongono di un utilizzo PSTN e non specificano un gateway PSTN. Tuttavia, non è possibile instradare effettivamente le chiamate su una route vocale che non dispone di questi due valori di proprietà configurati. Per questo motivo, potrebbe essere utile eseguire periodicamente questo comando, che restituisce l'identità di qualsiasi route vocale che non ha un utilizzo PSTN:

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

Analogamente, questo comando restituisce l'identità di qualsiasi route vocale che non è stata configurata per avere un gateway PSTN:

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>Verificare le impostazioni dell'operatore conferenza

Verificare le impostazioni dell'operatore di conferenza per le conferenze telefoniche con accesso esterno PSTN. Le impostazioni dell'operatore conferenza possono essere recuperate solo utilizzando il cmdlet **Get-CsDialInConferencingConfiguration** . Queste impostazioni non sono disponibili nel pannello di controllo di Lync Server. Per visualizzare le impostazioni dell'operatore conferenza, utilizzare un comando di Windows PowerShell simile al seguente, che restituisce la raccolta globale di impostazioni Operatore Conferenza:

`Get-CsDialInConferencingConfiguration -Identity "Global"`

Tenere presente che è possibile configurare le impostazioni dell'operatore conferenza anche nell'ambito del sito. Per restituire informazioni su tutte le impostazioni dell'operatore conferenza, utilizzare questo comando:

`Get-CsDialInConferencingConfiguration`

Il cmdlet Get-CsDialInConferencingConfiguration restituisce dati simili al seguente:

Identità: globale

EntryExitAnnouncementsType : UseNames

EnableNameRecording: true

EntryExitAnnouncementsEnabledByDefault: false

Se EntryExitAnnouncementsEnabledByDefault è impostato su false, significa che gli annunci per le conferenze sono disattivati. Per abilitare gli annunci di entrata e uscita, eseguire un comando di Windows PowerShell analogo al seguente:

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsSipDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsAccessEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[Get-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

