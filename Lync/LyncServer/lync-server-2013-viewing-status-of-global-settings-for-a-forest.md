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
ms.openlocfilehash: ec1dea4ad3d5052bc2ba23cccd9e19ab138414ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>Visualizzare lo stato delle impostazioni globali per una foresta in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-20_

Gli amministratori devono rivedere le impostazioni globali per una distribuzione di Lync Server 2013 mensili. L'obiettivo consiste nel rivedere le impostazioni implementate in base a un set di configurazioni note, una configurazione di base per garantire che le impostazioni siano valide e per determinare se la documentazione prevista deve essere aggiornata. Le modifiche apportate all'impostazione globale devono essere implementate tramite un processo di controllo delle modifiche che dovrebbe includere la documentazione delle nuove impostazioni.

Le impostazioni globali da rivedere sono descritte nelle sezioni seguenti:

<div>

## <a name="check-general-settings"></a>Controllare le impostazioni generali

Verificare le impostazioni generali, inclusi i domini SIP (Session Initiation Protocol) supportati per Lync Server 2013.

Le informazioni sul dominio SIP possono essere restituite tramite Windows PowerShell e il cmdlet **Get-CsSipDomain** . Per restituire queste informazioni, eseguire il `Get-CsSipDomain` comando di Windows PowerShell.

Get-CsSipDomain restituirà informazioni simili a quelle per tutti i domini SIP autorizzati:

Nome identità predefinito

\-------- ---- ---------

fabrikam.com fabrikam.com vero

na.fabrikam.com na.fabrikam.com false

Se la proprietà IsDefault è impostata su true, il dominio corrispondente è il dominio SIP predefinito. Puoi usare il cmdlet Set-CsSipDomain per cambiare il dominio SIP predefinito per l'organizzazione. Tuttavia, non è possibile eliminare semplicemente il dominio SIP predefinito, perché questo non è possibile senza un dominio predefinito. Se si vuole eliminare il dominio fabrikam.com, come illustrato nell'esempio precedente, è necessario prima di tutto configurare na.fabrikam.com come dominio predefinito.

</div>

<div>

## <a name="check-meeting-settings"></a>Verificare le impostazioni della riunione

Le impostazioni delle riunioni includono le definizioni dei criteri di riunione e il supporto per la partecipazione degli utenti anonimi alle riunioni.

Le impostazioni di configurazione della riunione possono essere recuperate tramite Windows PowerShell e il cmdlet **Get-CsMeetingConfiguration** . Ad esempio, questo comando restituisce informazioni sulle impostazioni di configurazione della riunione globale:

Get-CsMeetingConfiguration – Identity "Global" le impostazioni di configurazione delle riunioni possono essere configurate anche nell'ambito del sito. Per questo motivo, potresti voler usare il comando seguente, che restituisce informazioni su tutte le impostazioni di configurazione della riunione:

`Get-CsMeetingConfiguration`

Il cmdlet **Get-CsMeetingConfiguration** restituisce informazioni simili alle seguenti:

Identità: globale

PstnCallersBypassLobby: vero

EnableAssignedConferenceType: vero

DesignateAsPresenter: società

AssignedConferenceTypeByDefault: vero

AdmitAnonymousUsersByDefault: vero

Anche in questo caso, l'elemento finale nell'elenco, **AdmitAnonymousUsersByDefault**, Abilita o Disabilita la capacità degli utenti anonimi di partecipare alle riunioni.

Quando si verificano le impostazioni di configurazione della riunione, è possibile che sia utile confrontare le impostazioni correnti con quelle predefinite. È possibile visualizzare le impostazioni di configurazione della riunione predefinite eseguendo il comando seguente:

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

Il comando precedente crea un'istanza solo in memoria delle impostazioni di configurazione della riunione globale, un'istanza che usa il valore predefinito per ogni proprietà. Quando si esegue il comando non viene creata alcuna impostazione di configurazione della riunione effettiva. Tuttavia, tutti i valori di proprietà predefiniti verranno visualizzati sullo schermo.

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>Controllare i server Edge e le relative impostazioni

Le informazioni su Edge Server possono essere recuperate tramite Windows PowerShell. Questo comando restituisce informazioni su tutti i server perimetrali configurati per l'uso nell'organizzazione:

`Get-CsService -EdgeServer`

Le informazioni restituite includono tutte le impostazioni di FQDN e di porta per ogni server perimetrale:

Identità: EdgeServer: dc.fabrikam.com

Cancelliere: cancelliere: LYNC-SE.fabrikam.com

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

SiteId: sito: fabrikam. com

PoolFqdn: dc.fabrikam.com

Versione: 5

Ruolo: EdgeServer

<div>

## <a name="check-federation-settings"></a>Controllare le impostazioni della Federazione

Verificare le impostazioni della Federazione, ad esempio se è configurata e, se la risposta è "Sì", il nome di dominio completo e la porta. La Federazione viene abilitata e disabilitata tramite la raccolta globale delle impostazioni di configurazione di Access Edge. Tra le altre cose, significa che la Federazione è configurata in base a tutti o nulla: la Federazione è abilitata per l'intera organizzazione o la Federazione è disabilitata per l'intera organizzazione

Le impostazioni di configurazione di Access Edge possono essere restituite tramite Windows PowerShell. A tale scopo, eseguire il comando di Windows PowerShell seguente:

`Get-CsAccessEdgeConfiguration`

A sua volta, il comando restituirà dati simili a quelli seguenti:

Identità: globale

AllowAnonymousUsers: false

AllowFederatedUsers: false

AllowOutsideUsers: false

BeClearingHouse: false

EnablePartnerDiscovery: false

EnableArchivingDisclaimer: false

KeepCrlsUpToDateForPeers: vero

MarkSourceVerifiableOnOutgoingMessages: vero

OutgoingTlsCountForFederatedPartners: 4

RoutingMethod: UseDnsSrvRouting

Se la proprietà **AllowFederatedUsers** è impostata su true, significa che la Federazione è abilitata per l'organizzazione. L'impostazione di **AllowFederatedUsers** su true significa anche che in uno scenario di dominio diviso gli utenti locali saranno in grado di comunicare in modo uniforme con gli utenti in-the-cloud.

Per recuperare le impostazioni di FQDN e di porta per l'Edge Server, vedere l'attività precedente (Edge Server e le relative impostazioni).

L'abilitazione della Federazione nell'ambito globale indica che gli utenti possono comunicare potenzialmente con gli utenti federati. Per determinare se i singoli utenti possono effettivamente comunicare con gli utenti federati, è necessario esaminare i criteri di accesso degli utenti esterni assegnati all'utente.

Le informazioni di accesso degli utenti esterni possono essere restituite tramite Windows PowerShell. Ad esempio, questo comando restituisce le informazioni per il criterio di accesso utente esterno globale:

`Get-CsExternalAccessPolicy -Identity "Global"`

Questo comando restituisce le informazioni per tutti i criteri di accesso degli utenti esterni:

`Get-CsExternalAccessPolicy`

Le informazioni restituite saranno simili alle seguenti:

Identità: false

Descrizione

EnableFederationAccess: false

EnablePublicCloudAccess: false

EnablePublicCloudAccessAudioVideoAccess: false

EnableOutsideAccess: false

Se **EnableFederationAccess** è impostato su true, gli utenti gestiti dal criterio specifico possono comunicare con gli utenti federati.

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>Controllare le impostazioni di archiviazione

Controllare le impostazioni di archiviazione per le comunicazioni interne e federate. Prima di verificare le impostazioni per l'archiviazione interna ed esterna, è necessario verificare che l'archiviazione sia abilitata.

È possibile verificare le impostazioni di configurazione dell'archiviazione tramite Windows PowerShell e il cmdlet Get-CsArchivingConfiguration:

`Get-CsArchivingConfiguration -Identity "Global"`

Tieni presente che le impostazioni di archiviazione possono essere configurate anche nell'ambito del sito. Per restituire informazioni su tutte le impostazioni di archiviazione, usare questo comando:

`Get-CsArchivingConfiguration`

Il cmdlet Get-CsArchivingConfiguration restituisce i dati in modo simile al seguente:

Identità: globale

EnableArchiving: false

EnablePurging: false

PurgeExportedArchivesOnly: false

BlockOnArchiveFailure: false

KeepArchivingDataForDays: 14

PurgeHourOfDay: 2

ArchiveDuplicateMessages: vero

CachePurgingInterval: 24

Se la proprietà EnableArchiving è impostata su false, significa che non verranno archiviate sessioni di comunicazione. Se si vogliono archiviare solo le sessioni di messaggistica istantanea, usare un comando come il seguente per abilitare l'archiviazione delle sessioni di messaggistica istantanea:

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Per archiviare sessioni di conferenza e sessioni di messaggistica istantanea, usare questo comando:

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Se si vuole confrontare le impostazioni di archiviazione correnti con quelle predefinite, eseguire il comando di Windows PowerShell seguente:

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

Questo comando crea un'istanza solo in memoria delle impostazioni di configurazione dell'archiviazione globale. Non si tratta di una raccolta reale di impostazioni usate da Lync Server. Tuttavia, Visualizza i valori predefiniti per tutte le proprietà di configurazione dell'archiviazione.

Puoi anche usare questo comando per restituire il nome di dominio completo dei server di archiviazione:

`Get-CsService -ArchivingServer`

Dopo aver verificato che l'archiviazione sia abilitata, è possibile visualizzare i criteri di archiviazione per determinare se le sessioni di comunicazione interna ed esterna vengono archiviate.

Le informazioni sui criteri di archiviazione possono essere recuperate usando il cmdlet Get-CsArchivingPolicy. Ad esempio, questo comando restituisce informazioni sui criteri di archiviazione globale:

`Get-CsArchivingPolicy -Identity "Global"`

Poiché i criteri di archiviazione possono essere configurati anche nel sito e nell'ambito per utente, è anche possibile usare questo comando, che restituisce informazioni su tutti i criteri di archiviazione:

`Get-CsArchivingPolicy`

Le informazioni ricevute da Get-CsArchivingPolicy saranno simili alle seguenti:

Identità: globale

Descrizione

ArchiveInternal: false

ArchiveExternal: false

Tieni presente che, per impostazione predefinita, sia l'archiviazione interna che quella esterna sono disabilitate in un criterio di archiviazione.

</div>

<div>

## <a name="check-cdr-settings"></a>Controllare le impostazioni di CDR

Controllare le impostazioni del record di dettaglio delle chiamate (CDR) per la registrazione dei dettagli tra peer-to-peer, conferenze e chiamate vocali. Le informazioni dettagliate sulle impostazioni CDR possono essere restituite usando il cmdlet **Get-CsCdrConfiguration** . Ad esempio, questo comando restituisce informazioni sulla raccolta globale delle impostazioni di configurazione CDR:

`Get-CsCdrConfiguration -Identity "Global"`

Poiché CDR può essere configurato anche nell'ambito del sito, è anche possibile eseguire questo comando, che restituisce informazioni su tutte le impostazioni di configurazione CDR:

`Get-CsCdrConfiguration`

Il cmdlet Get-CsCdrConfiguration restituisce informazioni simili a queste per ogni raccolta di impostazioni di configurazione CDR:

Identità: globale

EnableCDR: vero

EnablePurging: vero

KeepCallDetailForDays: 60

KeepErrorReportForDays: 60

PurgeHourOfDay: 2

Le informazioni simili possono essere restituite per il monitoraggio QoE usando il cmdlet Get-CsQoEConfiguration. Ad esempio, questo comando restituisce informazioni sulla raccolta globale di impostazioni di configurazione QoE:

`Get-QoEConfiguration -Identity "Global"`

Queste informazioni saranno simili alle seguenti:

Identità: globale

ExternalConsumerIssuedCertId :

EnablePurging: vero

KeepQoEDataForDays: 60

PurgeHourOfDay: 1

EnableExternalConsumer: false

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE: vero

Se si vogliono confrontare le impostazioni di CDR correnti con quelle predefinite, è possibile rivedere i valori predefiniti eseguendo questo comando:

`New-CsCdrConfiguration -Identity "Global" -InMemory`

Allo stesso modo, i valori predefiniti per il monitoraggio QoE possono essere recuperati usando questo comando:

`New-CsQoEConfiguration -Identity "Global" -InMemory`

È anche possibile restituire il nome di dominio completo dei server di monitoraggio eseguendo questo comando:

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>Controllare le impostazioni vocali

Le impostazioni vocali in genere importanti per gli amministratori sono contenute nei criteri vocali e nelle route vocali: i criteri vocali contengono le impostazioni che determinano le funzionalità esposte ai singoli utenti, ad esempio la possibilità di inoltrare o trasferire le chiamate, mentre le route vocali determinano la modalità di routing delle chiamate (e se) attraverso la rete PSTN.

Le informazioni sui criteri vocali possono essere recuperate tramite Windows PowerShell. Ad esempio, questo comando restituisce informazioni sul criterio vocale globale:

`Get-CsVoicePolicy -Identity "Global"`

Questo comando restituisce informazioni su tutti i criteri vocali configurati per l'uso nell'organizzazione:

`Get-CsVoicePolicy`

Le informazioni restituite dal cmdlet Get-CsVoicePolicy sono simili alle seguenti:

Identità: globale

PstnUsages{}

Descrizione

AllowSimulRing: vero

AllowCallForwarding: vero

AllowPSTNReRouting: vero

Nome: DefaultPolicy

EnableDelegation: vero

EnableTeamCall: vero

EnableCallTransfer: vero

EnableCallPark: false

EnableMaliciousCallTracing: false

EnableBWPolicyOverride: false

PreventPSTNTollBypass: false

È anche possibile creare query che restituiscono un sottoinsieme dei criteri vocali. Ad esempio, questo comando restituisce tutti i criteri vocali che consentono l'inoltro di chiamata:

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

Questo comando restituisce tutti i criteri vocali che non consentono l'inoltro di chiamata:

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

In Windows PowerShell, usare il cmdlet Get-CsVoiceRouting per restituire informazioni sulle route vocali:

`Get-CsVoiceRoute`

Questo comando restituisce informazioni come questa per tutte le route vocali:

Identità: LocalRoute

Priorità: 0

Descrizione

NumberPattern: ^ (\\+ 1\[0-9\]{10}) $

PstnUsages{}

PstnGatewayList{}

Nome: LocalRoute

SuppressCallerId

AlternateCallerId

Lync Server consente di creare route vocali che non hanno un uso PSTN e non specificano un gateway PSTN. Tuttavia, non puoi effettivamente instradare le chiamate su una route vocale che non ha questi due valori di proprietà configurati. Per questo motivo, potresti trovare utile eseguire periodicamente questo comando, che restituisce l'identità di qualsiasi route vocale che non ha un uso PSTN:

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

Analogamente, questo comando restituisce l'identità di una route vocale non configurata per avere un gateway PSTN:

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>Controllare le impostazioni dell'operatore di conferenza

Controllare le impostazioni dell'operatore di conferenza per i servizi di conferenza telefonica con accesso esterno PSTN. Le impostazioni dell'operatore di conferenza possono essere recuperate solo usando il cmdlet **Get-CsDialInConferencingConfiguration** . Queste impostazioni non sono disponibili nel pannello di controllo di Lync Server. Per visualizzare le impostazioni di un operatore del servizio di conferenza, usare un comando di Windows PowerShell simile al seguente, che restituisce la raccolta globale delle impostazioni di operatore conferenza:

`Get-CsDialInConferencingConfiguration -Identity "Global"`

Tieni presente che le impostazioni dell'operatore di conferenza possono essere configurate anche nell'ambito del sito. Per restituire informazioni su tutte le impostazioni dell'operatore di conferenza, usare questo comando:

`Get-CsDialInConferencingConfiguration`

Il cmdlet Get-CsDialInConferencingConfiguration restituisce i dati in modo simile al seguente:

Identità: globale

EntryExitAnnouncementsType : UseNames

EnableNameRecording: vero

EntryExitAnnouncementsEnabledByDefault: false

Se EntryExitAnnouncementsEnabledByDefault è impostato su false, significa che gli annunci di conferenza sono disabilitati. Per abilitare gli annunci di entrata e di uscita, eseguire un comando di Windows PowerShell simile al seguente:

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

