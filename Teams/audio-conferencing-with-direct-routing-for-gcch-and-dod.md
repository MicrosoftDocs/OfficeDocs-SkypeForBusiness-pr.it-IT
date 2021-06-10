---
title: Audioconferenza con routing diretto, GCCH e DoD
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: L'amministratore può imparare a usare le audioconferenze con il routing diretto in ambienti GCCH e DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 577a9fe106cb5dae23049404b54433288e350b78
ms.sourcegitcommit: bd7847de9d1402476f8faaeae2ff97ec60d86a1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51262621"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audioconferenza con Instradamento diretto per GCC High e DoD

Le audioconferenze con routing diretto per GCC High e DoD consentono ai partecipanti di partecipare alle riunioni di Teams nell'organizzazione GCC High o DoD usando un dispositivo telefonico. I partecipanti alla riunione potrebbero scegliere di usare un dispositivo telefonico per partecipare Teams riunioni in scenari come quando la connettività Internet è limitata o quando gli utenti sono in viaggio e non hanno accesso Teams. I partecipanti possono scegliere di partecipare alle riunioni componendo l'accesso a un numero di telefono esterno per l'organizzazione o facendo in modo che la riunione sia con accesso esterno al dispositivo telefonico.

Con le audioconferenze con routing diretto per GCC High e DoD, l'organizzazione usa i propri numeri come numeri di telefono per l'accesso esterno e tutte le chiamate in uscita delle riunioni verso i dispositivi telefonici vengono instradati tramite Routing diretto. Per abilitare il servizio, le organizzazioni devono configurare Il routing diretto e configurare i numeri di telefono che possono essere usati come numeri di telefono per l'accesso esterno. Il requisito per l'uso del routing diretto è diverso dal servizio di audioconferenza offerto alle organizzazioni non GCC High e non DoD in cui i numeri di telefono per l'accesso esterno sono forniti da Microsoft.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Distribuire audioconferenze con routing diretto per GCC High e DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Passaggio 1: Ottenere audioconferenze con routing diretto per le GCC High o DoD 

Per usare le audioconferenze in GCC High o DoD, l'organizzazione e gli utenti dell'organizzazione devono avere una audioconferenza con la licenza Di routing diretto assegnata. Ecco le licenze necessarie per abilitare le audioconferenze con routing diretto GCC High o DoD.

- GCC Alta: una licenza per audioconferenza , GCC High Tenant per l'organizzazione e Audioconferenza, GCC licenze High per gli utenti.

- DoD: Audioconferenza - Licenza DoD Tenant per l'organizzazione e Audioconferenza - Licenze DoD per gli utenti.

Per abilitare il servizio sono necessarie una licenza tenant e almeno una licenza utente. Non è possibile abilitare il servizio solo con la licenza tenant o con solo licenze utente. Per ottenere licenze di servizio per il tenant e gli utenti dell'organizzazione, contattare il team dell'account.

> [!IMPORTANT]
> Gli utenti non possono essere abilitati per le audioconferenze con routing diretto finché non vengono impostati i numeri di telefono con accesso esterno. È consigliabile non assegnare audioconferenze con routing diretto per le licenze GCC High o DoD agli utenti fino a quando non si configurano i numeri di telefono per l'accesso esterno come descritto in questo articolo.  Se non si seguono queste indicazioni, la tastiera del telefono potrebbe risultare completamente mancante nel client Teams telefono.

### <a name="step-2-set-up-direct-routing"></a>Passaggio 2: Configurare il routing diretto

Per configurare il routing diretto, vedere gli articoli seguenti:

- [Pianificare Instradamento diretto](direct-routing-plan.md)

- [Configurare Instradamento diretto](direct-routing-configure.md)

> [!NOTE]
> Quando si configura il routing diretto, ricordarsi di usare i nomi fqdn e le porte GCC High o DoD specifici per le porte descritte in questi due articoli.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Passaggio 3: Configurare i numeri di telefono per l'accesso esterno

I numeri di telefono per l'accesso esterno sono i numeri di telefono associati al bridge di audioconferenza. Questi numeri vengono usati dai partecipanti per partecipare alle riunioni pianificate dagli utenti dell'organizzazione. Questi numeri sono inclusi anche negli inviti alle riunioni degli utenti che pianificano le riunioni nell'organizzazione e nella pagina "Trova un numero locale".

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Definire i numeri di telefono del servizio nel tenant

È possibile usare il cmdlet di PowerShell New-csHybridTelephoneNumber per definire i numeri di telefono del servizio nel tenant che possono essere usati per instradare le chiamate al servizio di audioconferenza tramite routing diretto. 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Ad esempio:
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Assegnare i numeri di telefono del servizio al bridge di audioconferenza dell'organizzazione

È possibile assegnare numeri di telefono di servizio al bridge di audioconferenza dell'organizzazione usando il cmdlet di PowerShell Register-csOnlineDialInConferencingServiceNumber.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

È possibile visualizzare l'ID del bridge di audioconferenza usando Get-CsOnlineDialInConferencingBridge. Ad esempio:

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Passaggio 4: Definire un criterio di routing vocale globale per abilitare il routing delle chiamate in uscita dalle riunioni

Il routing delle chiamate in uscita effettuate alla rete PSTN dalle riunioni organizzate dagli utenti dell'organizzazione è definito dal criterio di routing vocale globale dell'organizzazione. Se l'organizzazione ha definito un criterio di routing vocale globale, verificare che il criterio di routing vocale globale consenta le chiamate in uscita verso la rete PSTN che dovrebbero essere avviate da riunioni organizzate dagli utenti dell'organizzazione. Se nell'organizzazione non è definito un criterio di routing vocale globale, è necessario definirne uno per abilitare il routing delle chiamate in uscita alla rete PSTN dalle riunioni organizzate dagli utenti dell'organizzazione. Tenere presente che il criterio di routing vocale globale dell'organizzazione si applica anche alle chiamate uno-a-uno effettuate alla rete PSTN dagli utenti dell'organizzazione. Se le chiamate uno-a-uno alla rete PSTN sono abilitate per gli utenti dell'organizzazione, assicurarsi che il criterio di routing vocale globale soddisfi le esigenze dell'organizzazione per entrambi i tipi di chiamata. 

> [!NOTE]
> Location-Based routing non è disponibile nelle distribuzioni high Microsoft 365 Government Community Cloud (GCC) High o DoD. Quando si abilitano le audioconferenze, verificare che non siano abilitati gli utenti di audioconferenza negli ambienti GCC High o DoD per Location-Based Routing.

#### <a name="defining-a-global-voice-routing-policy"></a>Definizione di un criterio di routing vocale globale

È possibile definire un criterio di routing vocale globale definendo un utilizzo PSTN, una route vocale, un criterio di routing vocale e assegnando il nuovo criterio di routing vocale come criterio di routing vocale globale dell'organizzazione.

La procedura seguente descrive come definire un nuovo criterio di routing vocale globale per un'organizzazione senza uno. Se l'organizzazione ha già definito criteri di routing vocale, verificare che la configurazione seguente non sia in conflitto con i criteri di routing vocale esistenti dell'organizzazione.

Per creare un nuovo utilizzo PSTN in una sessione remota di PowerShell in Skype for Business Online, usare il comando seguente:

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Per altre informazioni, vedere [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage).

Per creare una nuova route vocale, usare il comando seguente:

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Quando si definisce una nuova route vocale per l'organizzazione, specificare uno o più gateway PSTN online PSTN definiti per l'organizzazione durante la configurazione del routing diretto. 

Lo schema dei numeri specifica quali chiamate verranno instradati attraverso l'elenco specificato di gateway in base al numero di telefono di destinazione della chiamata. Nell'esempio precedente, le chiamate verso qualsiasi destinazione nel mondo corrisponderanno al percorso vocale. Se si vuole limitare i numeri di telefono che è possibile comporre dalle riunioni degli utenti dell'organizzazione, è possibile modificare lo schema dei numeri in modo che la route vocale corrisponda solo ai modelli di numero delle destinazioni consentite. Tieni presente che se non ci sono route vocali che corrispondono al modello di numero del numero di telefono di destinazione di una determinata chiamata, la chiamata non verrà instradata.

Per altre informazioni, vedere [New-CsOnlineVoiceRoute.](/powershell/module/skype/new-csonlinevoiceroute)

Per creare un nuovo criterio di routing vocale, usare il comando seguente:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Se nel criterio di routing vocale vengono definiti più utilizzi PSTN, questi verranno valutati nell'ordine in cui sono definiti. È consigliabile che gli utilizzi PSTN siano definiti nell'ordine più specifico di quello più generico in termini di modelli di numero delle route vocali associate agli utilizzi PSTN. Ad esempio, se è stato definito un utilizzo PSTN per instradare le chiamate verso gli Stati Uniti e un altro utilizzo PSTN è stato definito per instradare le chiamate a qualsiasi altra località del mondo, l'utilizzo PSTN per le chiamate verso gli Stati Uniti dovrebbe essere elencato nei criteri di routing vocale prima dell'utilizzo pstn per instradare le chiamate a qualsiasi altra posizione nel mondo.

Per altre informazioni, vedere [New-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/new-csonlinevoiceroutingpolicy)

Per assegnare la nuova route vocale ai criteri globali di routing vocale dell'organizzazione, usare il comando seguente:

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Per altre informazioni, vedere [Grant-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

Dopo aver definito il criterio di routing vocale globale, le chiamate in uscita effettuate da riunioni organizzate dagli utenti dell'organizzazione verranno valutate in base alle route vocali associate agli utilizzi PSTN del criterio di routing vocale globale. Le chiamate in uscita verranno instradate in base alla prima route vocale che corrisponde al modello di numero del numero di telefono composto.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Passaggio 5: Assegnare audioconferenze con routing diretto GCC licenze High o DoD agli utenti

Per assegnare audioconferenze con routing diretto GCC licenze High o DoD all'utente, vedere [Assegnare licenze agli utenti](/microsoft-365/admin/manage/assign-licenses-to-users).

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Passaggio 6: (Facoltativo) Vedere un elenco di numeri di audioconferenza in Teams

Per visualizzare l'elenco dei numeri di audioconferenza dell'organizzazione, vedere Visualizzare un elenco di numeri di [audioconferenza in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Passaggio 7: (Facoltativo) Impostare le lingue dell'operatore automatico per i numeri di accesso esterno per i servizi di audioconferenza dell'organizzazione

Per cambiare le lingue dei numeri di accesso esterno per i servizi di audioconferenza dell'organizzazione, vedere Impostare le lingue degli operatori automatici per le audioconferenze [in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Passaggio 8: (Facoltativo) Modificare le impostazioni del bridge di audioconferenza dell'organizzazione

Per modificare le impostazioni del bridge di audioconferenza dell'organizzazione, vedere [Modificare le impostazioni per un bridge di audioconferenza.](change-the-settings-for-an-audio-conferencing-bridge.md)

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Passaggio 9: (Facoltativo) Impostare i numeri di telefono inclusi negli inviti alla riunione degli utenti dell'organizzazione

Per modificare il set di numeri di telefono inclusi negli inviti alla riunione degli utenti è l'organizzazione, vedere Impostare i numeri di telefono inclusi negli inviti [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Funzionalità di audioconferenza non supportate nelle audioconferenze con routing diretto GCC High e DoD

Di seguito sono riportate le funzionalità di audioconferenza non supportate nelle audioconferenze con routing diretto GCC High e DoD:

- Notifiche di entrata e uscita con la registrazione del nome. Per le audioconferenze con routing diretto, le notifiche di entrata e uscita vengono riprodotte nella riunione come toni.

- Criteri di restrizione delle chiamate in uscita per le audioconferenze. I controlli a livello utente per limitare le chiamate in uscita non sono applicabili alle chiamate in uscita instradati tramite Routing diretto.

- Disabilitare l'uso di numeri verde per l'organizzatore specifico delle riunioni. I controlli a livello utente per limitare l'uso di numeri verde per partecipare alle riunioni dell'organizzazione non sono applicabili alle chiamate instradati tramite Routing diretto.

- Invio di messaggi di posta elettronica di notifica agli utenti quando le impostazioni cambiano. I messaggi di posta elettronica di notifica delle audioconferenze non sono supportati per le audioconferenze con routing diretto GCC High e DoD.