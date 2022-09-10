---
title: Audioconferenza con routing diretto, GCCH e DoD
author: MicrosoftHeidi
ms.author: heidip
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
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Amministrazione informazioni su come usare le audioconferenze con routing diretto negli ambienti GCCH e DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd467b9da8d296c21d4a0405d651bbaa6b001fd3
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641777"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audioconferenza con Instradamento diretto per GCC High e DoD

Le audioconferenze con routing diretto per GCC High e DoD consentono ai partecipanti di partecipare alle riunioni di Teams nell'organizzazione GCC High o DoD usando un dispositivo telefonico. I partecipanti alla riunione potrebbero preferire usare un dispositivo telefonico per partecipare alle riunioni di Teams in scenari come quando la connettività Internet è limitata o quando gli utenti sono in viaggio e non hanno accesso a Teams. I partecipanti possono scegliere di partecipare alle riunioni effettuando l'accesso a un numero di telefono di accesso esterno per l'organizzazione o eseguendo la chiamata in uscita sul proprio dispositivo telefonico.

Con le audioconferenze con routing diretto per GCC High e DoD, l'organizzazione utilizza i propri numeri come numeri di telefono per l'accesso esterno e tutte le chiamate in uscita per le riunioni ai dispositivi telefonici vengono instradate tramite routing diretto. Per abilitare il servizio, le organizzazioni devono configurare l'instradamento diretto e configurare i numeri di telefono che possono essere utilizzati come numeri di telefono per l'accesso esterno. Il requisito per l'uso del routing diretto è diverso dal servizio di audioconferenza offerto alle organizzazioni non GCC High e non DoD in cui i numeri di telefono per l'accesso esterno sono forniti da Microsoft.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Distribuire audioconferenze con routing diretto per GCC High e DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Passaggio 1: Ottenere audioconferenze con routing diretto per licenze GCC High o DoD

Per utilizzare i servizi di audioconferenza in GCC High o DoD, l'organizzazione e gli utenti dell'organizzazione devono avere una licenza per l'audioconferenza con routing diretto assegnata. Ecco le licenze necessarie per abilitare le audioconferenze con routing diretto per GCC High o DoD.

- GCC High: una licenza GCC High Tenant per i servizi di audioconferenza per l'organizzazione e le licenze GCC High per gli utenti.

- DoD: una licenza per audioconferenza - DoD Tenant per l'organizzazione e audioconferenza - licenze DoD per gli utenti.

Per abilitare il servizio sono necessarie una licenza tenant e almeno una licenza utente. Non è possibile abilitare il servizio solo con la licenza tenant o solo con licenze utente. Per ottenere licenze di servizio per il tenant e gli utenti dell'organizzazione, contattare il team degli account.

> [!IMPORTANT]
> Gli utenti non possono essere abilitati per le audioconferenze con routing diretto fino a quando non vengono configurati i numeri di telefono per l'accesso esterno. Ti consigliamo di non assegnare audioconferenze con routing diretto per licenze GCC High o DoD agli utenti fino a quando non configuri i numeri di telefono per l'accesso esterno, come descritto in questo articolo.  Se non si seguono queste indicazioni, la tastiera del telefono potrebbe risultare completamente mancante nel client di Teams.

### <a name="step-2-set-up-direct-routing"></a>Passaggio 2: Configurare il routing diretto

Per configurare l'instradamento diretto, vedere gli articoli seguenti:

- [Pianificare Instradamento diretto](direct-routing-plan.md)

- [Configurare Instradamento diretto](direct-routing-configure.md)

> [!NOTE]
> Quando si configura il routing diretto, ricordarsi di usare le porte e i nomi FQDN specifici di GCC High o DoD descritti in questi due articoli.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Passaggio 3: Configurare i numeri di telefono per l'accesso esterno

I numeri di telefono per l'accesso esterno sono i numeri di telefono associati al bridge di audioconferenza. Questi numeri vengono usati dai partecipanti per partecipare alle riunioni pianificate dagli utenti dell'organizzazione. Questi numeri sono inclusi anche negli inviti alle riunioni degli utenti che pianificano riunioni nell'organizzazione e nella pagina "Trova un numero locale".

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Definire i numeri di telefono di servizio nel tenant

Puoi utilizzare il cmdlet PowerShell New-csHybridTelephoneNumber per definire i numeri di telefono di servizio nel tenant che possono essere usati per instradare le chiamate al servizio Di audioconferenza tramite routing diretto.

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Ad esempio:

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Assegnare i numeri di servizio al bridge di audioconferenza dell'organizzazione

Puoi assegnare i numeri di telefono di servizio al bridge di audioconferenza della tua organizzazione utilizzando il cmdlet PowerShell Register-csOnlineDialInConferencingServiceNumber.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Puoi visualizzare l'ID del bridge di audioconferenza utilizzando Get-CsOnlineDialInConferencingBridge. Ad esempio:

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Passaggio 4: Definire un criterio di routing vocale globale per abilitare il routing delle chiamate in uscita dalle riunioni

Il routing delle chiamate in uscita effettuate al pstn dalle riunioni organizzate dagli utenti dell'organizzazione è definito dai criteri di routing vocale globale dell'organizzazione. Se l'organizzazione ha definito un criterio di routing vocale globale, verificare che il criterio di routing vocale globale consenta le chiamate in uscita alla rete PSTN che dovrebbero essere avviate dalle riunioni organizzate dagli utenti dell'organizzazione. Se nell'organizzazione non è definito un criterio di routing vocale globale, è necessario definirne uno per abilitare il routing delle chiamate in uscita alla rete PSTN dalle riunioni organizzate dagli utenti dell'organizzazione. Si noti che i criteri di routing vocale globale dell'organizzazione si applicano anche alle chiamate uno-a-uno effettuate alla rete PSTN dagli utenti dell'organizzazione. Se le chiamate uno-a-uno al PSTN sono abilitate per gli utenti dell'organizzazione, assicurarsi che il criterio di routing vocale globale soddisfi le esigenze dell'organizzazione per entrambi i tipi di chiamate.

> [!NOTE]
> Location-Based Routing non è disponibile nelle distribuzioni Microsoft 365 Government Community Cloud (GCC) High o DoD. Quando si abilitano le audioconferenze, verifica che nessun utente di audioconferenza in GCC High o negli ambienti DoD sia abilitato per Location-Based Routing.

#### <a name="defining-a-global-voice-routing-policy"></a>Definizione di un criterio di routing vocale globale

Un criterio di routing vocale globale può essere definito definendo un utilizzo PSTN, una route vocale, un criterio di routing vocale e assegnando i nuovi criteri di routing vocale come criteri di routing vocale globale dell'organizzazione.

I passaggi seguenti descrivono come definire un nuovo criterio di routing vocale globale per un'organizzazione senza criteri. Se l'organizzazione ha già definito criteri di routing vocale, verificare che la configurazione seguente non sia in conflitto con i criteri di routing vocale esistenti dell'organizzazione.

Per creare un nuovo utilizzo PSTN in una sessione remota di PowerShell in Teams, usare il comando seguente:

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Per ulteriori informazioni, vedi [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage).

Per creare una nuova route vocale, usa il comando seguente:

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Quando si definisce una nuova route vocale per l'organizzazione, specificare uno o più gateway PSTN pstn online PSTN definiti per l'organizzazione durante la configurazione del routing diretto.

Il modello di numero specifica quali chiamate verranno instradate attraverso l'elenco di gateway specificato in base al numero di telefono di destinazione della chiamata. Nell'esempio precedente, le chiamate a qualsiasi destinazione nel mondo corrisponderanno al percorso vocale. Se si vogliono limitare i numeri di telefono che è possibile comporre dalle riunioni degli utenti dell'organizzazione, è possibile modificare il modello di numero in modo che il percorso vocale corrisponda solo ai modelli di numero delle destinazioni consentite. Si noti che se non ci sono route vocali che corrispondono al modello di numero del numero di telefono di destinazione di una determinata chiamata, la chiamata non verrà instradata.

Per ulteriori informazioni, vedi [New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute).

Per creare un nuovo criterio di routing vocale, usare il comando seguente:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Se vengono definiti più utilizzi PSTN nei criteri di routing vocale, verranno valutati nell'ordine in cui sono definiti. È consigliabile definire gli utilizzi PSTN nell'ordine dei più specifici per i più generici in termini di modelli numerici delle route vocali associate agli utilizzi PSTN. Ad esempio, se è stato definito un utilizzo PSTN per instradare le chiamate alla Stati Uniti e un altro utilizzo di PSTN è stato definito per instradare le chiamate a qualsiasi altra posizione nel mondo, l'utilizzo PSTN per le chiamate al Stati Uniti dovrebbe essere elencato nei criteri di routing vocale prima dell'utilizzo di PSTN per instradare le chiamate a qualsiasi altra posizione nel mondo.

Per ulteriori informazioni, vedi [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).

Per assegnare la nuova route vocale al criterio di routing vocale globale dell'organizzazione, usare il comando seguente:

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Per ulteriori informazioni, vedi [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

Una volta definito il criterio di routing vocale globale, tutte le chiamate in uscita effettuate dalle riunioni organizzate dagli utenti dell'organizzazione verranno valutate rispetto alle route vocali associate agli utilizzi PSTN dei criteri di routing vocale globale. Le chiamate in uscita verranno instradate in base al primo percorso vocale che corrisponde al modello di numero del numero di telefono composto.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Passaggio 5: Assegnare audioconferenze con routing diretto per licenze GCC High o DoD agli utenti

Per assegnare audioconferenze con routing diretto per licenze GCC High o DoD all'utente, vedi [Assegnare licenze agli utenti](/microsoft-365/admin/manage/assign-licenses-to-users).

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Passaggio 6: (Facoltativo) Visualizzare un elenco dei numeri dei servizi di audioconferenza in Teams

Per visualizzare l'elenco dei numeri dei servizi di audioconferenza della tua organizzazione, vai a [Visualizzare un elenco dei numeri dei servizi di audioconferenza in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Passaggio 7: (Facoltativo) Impostare le lingue dell'operatore automatico per i numeri di accesso esterno per i servizi di audioconferenza dell'organizzazione

Per cambiare le lingue dei numeri di accesso esterno per i servizi di audioconferenza dell'organizzazione, vedere [Impostare le lingue dell'operatore automatico per le audioconferenze in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Passaggio 8: (Facoltativo) Modificare le impostazioni del bridge audioconferenza dell'organizzazione

Per modificare le impostazioni del bridge di audioconferenza dell'organizzazione, vedi [Modificare le impostazioni per un bridge di audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md).

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Passaggio 9: (Facoltativo) Impostare i numeri di telefono inclusi negli inviti alle riunioni degli utenti dell'organizzazione

Per modificare il set di numeri di telefono inclusi negli inviti alle riunioni degli utenti è l'organizzazione, vedere [Impostare i numeri di telefono inclusi negli inviti in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Funzionalità di audioconferenza non supportate nelle audioconferenze con routing diretto per GCC High e DoD

Di seguito sono indicate le funzionalità di audioconferenza non supportate nelle audioconferenze con routing diretto per GCC High e DoD:

- Notifiche di entrata e uscita tramite la registrazione del nome. Per le audioconferenze con routing diretto, le notifiche di accesso e uscita vengono riprodotte nella riunione come toni.

- Disabilita l'uso dei numeri verdi per l'organizzatore specifico delle riunioni. I controlli a livello utente per limitare l'uso dei numeri verdi per partecipare alle riunioni dell'organizzazione non sono applicabili alle chiamate instradate tramite routing diretto.

- Invio di messaggi di posta elettronica di notifica agli utenti in caso di modifica delle impostazioni. I messaggi di posta elettronica di notifica per le audioconferenze non sono supportati per le audioconferenze con routing diretto per GCC High e DoD.
