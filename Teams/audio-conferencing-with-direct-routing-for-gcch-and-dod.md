---
title: Audioconferenza con instradamento diretto, MCCH e DoD
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
description: L'amministratore può imparare a usare le audioconferenze con il routing diretto in ambienti MCCH e DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 818b36e379532e361fd3991b002bc899156af056
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812916"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audioconferenza con Instradamento diretto per GCC High e DoD

Le audioconferenze con routing diretto per GCC High e DoD consentono ai partecipanti di partecipare alle riunioni di Teams nell'organizzazione GCC High o DoD utilizzando un dispositivo telefonico. I partecipanti alla riunione potrebbero preferire usare un dispositivo telefonico per partecipare alle riunioni di Teams in scenari come quando la connettività Internet è limitata o quando gli utenti sono in viaggio e non hanno accesso a Teams. I partecipanti possono scegliere di partecipare alle riunioni componendo un numero di telefono per l'organizzazione o facendo in modo che la riunione sia in uscita sul proprio dispositivo telefonico.

Con le audioconferenze con routing diretto per GCC High e DoD, l'organizzazione usa i propri numeri come numeri di telefono per l'accesso esterno e tutte le chiamate in uscita per le riunioni verso i dispositivi telefonici vengono instradati tramite l'instradamento diretto. Per abilitare il servizio, le organizzazioni devono configurare l'instradamento diretto e configurare i numeri di telefono che possono essere utilizzati come numeri di telefono per l'accesso esterno. Il requisito di usare l'instradamento diretto è diverso dal servizio di audioconferenza offerto alle organizzazioni non GCC High e non DoD in cui i numeri di telefono per l'accesso esterno sono forniti da Microsoft.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Distribuire le audioconferenze con l'instradamento diretto per GCC High e DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Passaggio 1: Ottenere l'audioconferenza con l'instradamento diretto per le licenze GCC High o DoD 

Per utilizzare le audioconferenze in GCC High o DoD, è necessario che all'organizzazione e agli utenti dell'organizzazione sia assegnata una licenza per l'instradamento diretto. Ecco le licenze necessarie per abilitare l'audioconferenza con l'instradamento diretto per GCC High o DoD.

- GCC High: audioconferenza - licenza GCC High Tenant per l'organizzazione e Audioconferenza - Licenze GCC High per gli utenti.

- DoD: Una licenza di audioconferenza - Licenza DoD Tenant per l'organizzazione e Audioconferenza - Licenze DoD per gli utenti.

Per abilitare il servizio sono necessarie una licenza tenant e almeno una licenza utente. Non è possibile abilitare il servizio solo con la licenza tenant o solo con licenze utente. Per ottenere licenze di servizio per il tenant e gli utenti dell'organizzazione, contattare il team dell'account.

> [!IMPORTANT]
> Gli utenti non possono essere abilitati per le audioconferenze con instradamento diretto fino alla configurazione dei numeri di telefono per l'accesso esterno. È consigliabile non assegnare agli utenti le audioconferenze con routing diretto per le licenze GCC High o DoD fino a quando non si configurano i numeri di telefono per l'accesso esterno, come descritto in questo articolo.

### <a name="step-2-set-up-direct-routing"></a>Passaggio 2: Configurare l'instradamento diretto

Per configurare l'instradamento diretto, vedere gli articoli seguenti:

- [Pianificare Instradamento diretto](direct-routing-plan.md)

- [Configurare Instradamento diretto](direct-routing-configure.md)

> [!NOTE]
> Quando si configura il routing diretto, ricordarsi di usare gli FQDN e le porte GCC High o DoD specifici, descritti in questi due articoli.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Passaggio 3: Configurare i numeri di telefono per l'accesso esterno

I numeri di telefono per l'accesso esterno sono i numeri di telefono associati al bridge per audioconferenza. Questi numeri vengono utilizzati dai partecipanti per partecipare alle riunioni pianificate dagli utenti dell'organizzazione. Questi numeri sono inclusi anche negli inviti alle riunioni degli utenti che pianificano le riunioni nell'organizzazione e nella pagina "Trova un numero locale".

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Definire i numeri di telefono di servizio nel tenant

Puoi usare il cmdlet PowerShell New-csHybridTelephoneNumber per definire i numeri di servizio del tuo tenant che possono essere usati per instradare le chiamate al servizio Audioconferenza tramite l'instradamento diretto. 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Ad esempio:
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Assegnare i numeri di servizio al bridge per audioconferenza dell'organizzazione

Puoi assegnare numeri di servizio al bridge di Audioconferenza della tua organizzazione utilizzando il cmdlet di PowerShell Register-csOnlineDialInConferencingServiceNumber.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Puoi visualizzare l'ID del bridge di audioconferenza utilizzando Get-CsOnlineDialInConferencingBridge. Ad esempio:

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Passaggio 4: Definire un criterio di routing vocale globale per abilitare il routing delle chiamate in uscita dalle riunioni

Il routing delle chiamate in uscita effettuate alla rete PSTN dalle riunioni organizzate dagli utenti dell'organizzazione è definito dai criteri di routing vocale globale dell'organizzazione. Se la tua organizzazione ha definito un criterio di routing vocale globale, verifica che il criterio di routing vocale globale consenta le chiamate in uscita alla rete PSTN che dovrebbero essere avviate da riunioni organizzate dagli utenti dell'organizzazione. Se l'organizzazione non ha definito un criterio di routing vocale globale, è necessario definirne uno per abilitare l'instradamento delle chiamate in uscita alla rete PSTN da riunioni organizzate dagli utenti dell'organizzazione. I criteri di routing vocale globale dell'organizzazione si applicano anche alle chiamate uno-a-uno effettuate alla rete PSTN dagli utenti dell'organizzazione. Se le chiamate uno-a-uno alla rete PSTN sono abilitate per gli utenti dell'organizzazione, assicurati che il criterio di routing vocale globale soddisfi le esigenze dell'organizzazione per entrambi i tipi di chiamata. 

> [!NOTE]
> Location-Based routing delle chiamate non è disponibile nelle distribuzioni High o DoD di Microsoft 365 Government Community Cloud (GCC). Quando si abilitano le audioconferenze, verificare che nessun utente di Audioconferenza sia abilitato per il routing Location-Based GCC.

#### <a name="defining-a-global-voice-routing-policy"></a>Definizione di un criterio di routing vocale globale

Un criterio di routing vocale globale può essere definito definendo l'utilizzo di PSTN, un percorso vocale, un criterio di routing vocale e assegnando il nuovo criterio di routing vocale come criterio di routing vocale globale dell'organizzazione.

I passaggi seguenti descrivono come definire un nuovo criterio di routing vocale globale per un'organizzazione senza uno. Se l'organizzazione ha già definito criteri di routing vocale, verificare che la configurazione seguente non sia in conflitto con i criteri di routing vocale esistenti dell'organizzazione.

Per creare un nuovo utilizzo di PSTN in una sessione remota di PowerShell in Skype for Business online, usare il comando seguente:

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Per ulteriori informazioni, consulta [Set-CsOnlinePstnUsage.](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage)

Per creare una nuova route vocale, usare il comando seguente:

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Quando si definisce una nuova route vocale per l'organizzazione, specificare uno o più gateway PSTN online PSTN definiti per l'organizzazione durante la configurazione del routing diretto. 

Il modello di numero specifica quali chiamate verranno instradati attraverso l'elenco specificato di gateway in base al numero di telefono di destinazione della chiamata. Nell'esempio precedente, le chiamate verso tutte le destinazioni nel mondo corrisponderanno al percorso vocale. Se si desidera limitare i numeri di telefono che è possibile comporre dalle riunioni degli utenti dell'organizzazione, è possibile modificare il modello di numero in modo che il percorso vocale corrisponda solo ai modelli di numero delle destinazioni consentite. Tenere presente che se non sono presenti percorsi vocali che corrispondono al modello di numero del numero di telefono di destinazione di una determinata chiamata, la chiamata non verrà instradata.

Per ulteriori informazioni, consulta [New-CsOnlineVoiceRoute.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute)

Per creare un nuovo criterio di routing vocale, usare il comando seguente:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Se nel criterio di routing vocale vengono definiti più utilizzi pstN, questi vengono valutati nell'ordine in cui sono stati definiti. È consigliabile che gli utilizzi di PSTN siano definiti nell'ordine dei più specifici per i più generici in termini di modelli numerici delle route vocali associate agli utilizzi PSTN. Ad esempio, se un utilizzo PSTN è stato definito per instradare le chiamate verso gli Stati Uniti e un altro utilizzo PSTN è stato definito per instradare le chiamate a qualsiasi altra località del mondo, l'utilizzo di PSTN per le chiamate verso gli Stati Uniti dovrebbe essere elencato nei criteri di routing vocale in anticipo rispetto all'utilizzo di PSTN per instradare le chiamate verso qualsiasi altra località del mondo.

Per ulteriori informazioni, consulta [New-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)

Per assegnare il nuovo percorso vocale al criterio di routing vocale globale dell'organizzazione, usare il comando seguente:

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Per ulteriori informazioni, consulta [Grant-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

Una volta definito il criterio di routing vocale globale, le chiamate in uscita effettuate dalle riunioni organizzate dagli utenti dell'organizzazione verranno valutate rispetto ai percorsi vocali associati agli utilizzi PSTN del criterio di routing vocale globale. Le chiamate in uscita verranno instradate in base al primo percorso vocale che corrisponde al modello di numero del numero di telefono composto.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Passaggio 5: Assegnare audioconferenze con routing diretto per le licenze GCC High o DoD agli utenti

Per assegnare le audioconferenze con routing diretto per le licenze GCC High o DoD all'utente, vedi [Assegnare licenze agli utenti.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Passaggio 6: (Facoltativo) Visualizzare un elenco di numeri per i servizi di audioconferenza in Teams

Per visualizzare l'elenco dei numeri dei servizi di audioconferenza dell'organizzazione, vedere l'elenco dei numeri dei servizi di [audioconferenza in Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Passaggio 7: (Facoltativo) Impostare le lingue dell'operatore automatico per i numeri di accesso esterno per i servizi di audioconferenza dell'organizzazione

Per cambiare le lingue dei numeri di accesso esterno per i servizi di audioconferenza dell'organizzazione, consulta Impostare le lingue dell'operatore automatico per le audioconferenze [in Microsoft Teams.](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Passaggio 8: (Facoltativo) Modificare le impostazioni del bridge di audioconferenza dell'organizzazione

Per modificare le impostazioni del bridge di audioconferenza dell'organizzazione, vedi Modificare le impostazioni [per un bridge per audioconferenza.](change-the-settings-for-an-audio-conferencing-bridge.md)

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Passaggio 9: (Facoltativo) Impostare i numeri di telefono inclusi negli inviti alle riunioni degli utenti dell'organizzazione

Per modificare il set di numeri di telefono inclusi negli inviti alle riunioni degli utenti è la tua organizzazione, vedi Impostare i numeri di telefono inclusi negli inviti [in Microsoft Teams.](set-the-phone-numbers-included-on-invites-in-teams.md)

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Le funzionalità di audioconferenza non sono supportate nelle audioconferenze con routing diretto per GCC High e DoD

Di seguito sono riportate le funzionalità di audioconferenza non supportate nelle audioconferenze con instradamento diretto per GCC High e DoD:

- Notifiche di accesso e uscita tramite registrazione del nome. Per le audioconferenze con instradamento diretto, le notifiche di accesso e uscita vengono riprodotte nella riunione come toni.

- Criteri di restrizione delle chiamate in uscita per le audioconferenze. I controlli a livello utente per limitare le chiamate in uscita non sono applicabili alle chiamate in uscita instradati tramite instradamento diretto.

- Disabilita l'uso dei numeri verde per le riunioni con l'organizzatore specifico. I controlli a livello utente che limitano l'uso dei numeri verde per partecipare alle riunioni dell'organizzazione non sono applicabili alle chiamate instradati tramite instradamento diretto.

- Invio di messaggi di posta elettronica di notifica agli utenti quando le impostazioni vengono modificate. I messaggi di posta elettronica di notifica per le audioconferenze non sono supportati per le audioconferenze con instradamento diretto per GCC High e DoD.
