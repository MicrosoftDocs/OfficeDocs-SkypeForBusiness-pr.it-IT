---
title: Servizi di conferenza audio con routing diretto, GCCH e DoD
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
description: L'amministratore può trovare informazioni su come usare i servizi di audioconferenza con routing diretto in ambienti GCCH e DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 818b36e379532e361fd3991b002bc899156af056
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812916"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audioconferenza con Instradamento diretto per GCC High e DoD

I servizi di audioconferenza con routing diretto per GCC High e DoD consentono ai partecipanti di partecipare a riunioni di teams nell'organizzazione GCC High o DoD usando un dispositivo telefonico. I partecipanti alla riunione possono preferire l'uso di un dispositivo telefonico per partecipare a riunioni di team in scenari come la connettività Internet è limitata o quando gli utenti sono in viaggio e non hanno accesso ai team. I partecipanti possono scegliere di partecipare alle riunioni effettuando la chiamata in un numero di telefono di accesso esterno per l'organizzazione oppure effettuando la chiamata della riunione al dispositivo telefonico.

Con i servizi di audioconferenza con routing diretto per GCC High e DoD, l'organizzazione usa i propri numeri come numeri di telefono di accesso esterno e tutti i dial-out per le riunioni vengono instradati tramite routing diretto. Per abilitare il servizio, le organizzazioni devono impostare il routing diretto e configurare i numeri di telefono che possono essere usati come numeri di telefono di accesso esterno. Il requisito di usare il routing diretto è diverso dal servizio di audioconferenza offerto alle organizzazioni non-GCC High e non-DoD in cui i numeri di telefono di accesso esterno sono forniti da Microsoft.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Distribuire servizi di audioconferenza con routing diretto per GCC High e DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Passaggio 1: ottenere servizi di audioconferenza con routing diretto per le licenze GCC High o DoD 

Per usare le conferenze audio in GCC High o DoD, l'organizzazione e gli utenti dell'organizzazione devono avere un servizio di audioconferenza con licenza di routing diretta assegnata. Ecco le licenze necessarie per abilitare i servizi di audioconferenza con routing diretto per GCC High o DoD.

- GCC High: una licenza per i servizi di audioconferenza per l'organizzazione e l'audioconferenza-licenze GCC High per gli utenti.

- DoD: una licenza per i servizi di audioconferenza-DoD tenant per l'organizzazione e le licenze per i servizi di audioconferenza per gli utenti.

Per abilitare il servizio, è necessaria una licenza tenant e almeno una licenza per l'utente. Non è possibile abilitare il servizio con solo la licenza tenant o solo con le licenze utente. Per ottenere le licenze di servizio per il tenant e gli utenti dell'organizzazione, contattare il team dell'account.

> [!IMPORTANT]
> Gli utenti non possono essere abilitati per i servizi di audioconferenza con routing diretto fino alla configurazione dei numeri di telefono di accesso esterno. È consigliabile non assegnare servizi di audioconferenza con routing diretto per le licenze GCC High o DoD agli utenti fino a quando non si configurano i numeri di telefono con accesso esterno come descritto in questo articolo.

### <a name="step-2-set-up-direct-routing"></a>Passaggio 2: configurare il routing diretto

Per configurare il routing diretto, vedere gli articoli seguenti:

- [Pianificare Instradamento diretto](direct-routing-plan.md)

- [Configurare Instradamento diretto](direct-routing-configure.md)

> [!NOTE]
> Quando configuri il routing diretto, ricordati di usare gli FQDN e le porte di dominio elevato o specifico del DoD che sono descritti in questi due articoli.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Passaggio 3: configurare i numeri di telefono con accesso esterno

I numeri di telefono di accesso esterno sono i numeri di telefono associati al Bridge di audioconferenza. Questi numeri vengono usati dai partecipanti per partecipare alle riunioni pianificate dagli utenti dell'organizzazione. Questi numeri sono inclusi anche negli inviti alla riunione degli utenti che pianificano le riunioni nell'organizzazione e nella pagina "trova un numero locale".

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Definire i numeri di telefono del servizio nel tenant

Puoi usare il cmdlet di PowerShell New-csHybridTelephoneNumber per definire i numeri di telefono del servizio nel tenant che possono essere usati per instradare le chiamate al servizio di audioconferenza tramite routing diretto. 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Ad esempio:
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Assegnare i numeri di telefono del servizio al Bridge di audioconferenza dell'organizzazione

È possibile assegnare numeri di telefono del servizio al Bridge di audioconferenza dell'organizzazione usando il cmdlet Register-csOnlineDialInConferencingServiceNumber di PowerShell.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Puoi vedere l'ID del Bridge di audioconferenza usando Get-CsOnlineDialInConferencingBridge. Ad esempio:

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Passaggio 4: definire un criterio di routing vocale globale per consentire il routing delle chiamate in uscita dalle riunioni

Il routing delle chiamate in uscita effettuate alla rete PSTN da riunioni organizzate dagli utenti dell'organizzazione è definito dal criterio di routing vocale globale dell'organizzazione. Se l'organizzazione ha un criterio di routing vocale globale definito, verificare che i criteri di routing vocale globale consentano alle chiamate in uscita alla rete PSTN che dovrebbero essere avviate da riunioni organizzate dagli utenti dell'organizzazione. Se l'organizzazione non ha un criterio di routing vocale globale definito, sarà necessario definirne uno per consentire il routing delle chiamate in uscita alla rete PSTN dalle riunioni organizzate dagli utenti dell'organizzazione. Tieni presente che il criterio di routing vocale globale dell'organizzazione si applica anche alle chiamate uno-a-uno effettuate alla rete PSTN dagli utenti dell'organizzazione. Se le chiamate uno-a-uno alla rete PSTN sono abilitate per gli utenti dell'organizzazione, verificare che il criterio di routing vocale globale soddisfi le esigenze dell'organizzazione per entrambi i tipi di chiamate. 

> [!NOTE]
> Location-Based routing non è disponibile nelle distribuzioni di Microsoft 365 Government community Cloud (GCC) High o DoD. Quando si Abilita la conferenza audio, verificare che non siano abilitati utenti di servizi di audioconferenza nell'ambiente GCC High o DoD per Location-Based routing.

#### <a name="defining-a-global-voice-routing-policy"></a>Definizione di un criterio di routing vocale globale

Un criterio di routing vocale globale può essere definito definendo un uso PSTN, una route vocale, un criterio di routing vocale e assegnando i nuovi criteri di routing vocale come criterio di routing vocale globale dell'organizzazione.

I passaggi seguenti descrivono come definire un nuovo criterio di routing vocale globale per un'organizzazione senza una. Se l'organizzazione dispone già di criteri di routing vocale definiti, verificare che la configurazione seguente non sia in conflitto con i criteri di routing vocale esistenti dell'organizzazione.

Per creare un nuovo utilizzo PSTN in una sessione remota di PowerShell in Skype for business online, usare il comando seguente:

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Per altre informazioni, vedere [set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).

Per creare una nuova route vocale, usare il comando seguente:

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Quando si definisce una nuova route vocale per l'organizzazione, specificare uno o più gateway PSTN online PSTN definiti per l'organizzazione durante la configurazione del routing diretto. 

Il modello di numero specifica le chiamate che verranno instradate tramite l'elenco di gateway specificato in base al numero di telefono di destinazione della chiamata. Nell'esempio precedente le chiamate a qualsiasi destinazione nel mondo corrisponderanno alla route vocale. Per limitare i numeri di telefono che possono essere comunicati dalle riunioni degli utenti dell'organizzazione, è possibile modificare il modello di numero in modo che la route vocale corrisponda solo agli schemi di numero delle destinazioni consentite. Tieni presente che se non ci sono route vocali che corrispondono al modello numerico del numero di telefono di destinazione di una determinata chiamata, la chiamata non verrà instradata.

Per altre informazioni, vedere [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).

Per creare un nuovo criterio di routing vocale, usare il comando seguente:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Se nel criterio di routing vocale vengono definiti più usi PSTN, questi verranno valutati nell'ordine in cui sono definiti. È consigliabile che gli usi PSTN siano definiti nell'ordine più specifico per il più generico in termini di pattern di numero delle route vocali associate agli usi PSTN. Ad esempio, se è stato definito un uso PSTN per instradare le chiamate agli Stati Uniti e un altro utilizzo PSTN è stato definito per instradare le chiamate a qualsiasi altra posizione nel mondo, l'utilizzo PSTN per le chiamate agli Stati Uniti deve essere elencato nei criteri di routing vocale prima dell'uso PSTN per instradare le chiamate a qualsiasi altra posizione nel mondo.

Per altre informazioni, vedere [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).

Per assegnare la nuova route vocale al criterio di routing vocale globale dell'organizzazione, usare il comando seguente:

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Per altre informazioni, vedere [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

Una volta definiti i criteri di routing vocale globale, le chiamate in uscita effettuate dalle riunioni organizzate dagli utenti dell'organizzazione verranno valutate in base alle route vocali associate agli usi PSTN del criterio di routing vocale globale. Le chiamate in uscita verranno instradate in base alla prima route vocale che corrisponde al modello numerico del numero di telefono chiamato.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Passaggio 5: assegnare servizi di audioconferenza con routing diretto per le licenze GCC High o DoD agli utenti

Per assegnare i servizi di audioconferenza con routing diretto per le licenze GCC High o DoD all'utente, vedere [assegnare licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Passaggio 6: (facoltativo) visualizzare un elenco di numeri di conferenza audio in teams

Per visualizzare l'elenco dei numeri di servizi di audioconferenza dell'organizzazione, [vedere un elenco di numeri di conferenza audio in Microsoft teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Passaggio 7: (facoltativo) impostare le lingue per gli operatori automatici per i numeri di accesso esterno per i servizi di audioconferenza dell'organizzazione

Per modificare le lingue dei numeri di accesso esterno per i servizi di audioconferenza dell'organizzazione, vedere [impostare le lingue per l'operatore automatico per i servizi di audioconferenza in Microsoft teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Passaggio 8: (facoltativo) modificare le impostazioni del Bridge di audioconferenza dell'organizzazione

Per modificare le impostazioni del Bridge di audioconferenza dell'organizzazione, vedere [modificare le impostazioni per un Bridge di audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md).

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Passaggio 9: (facoltativo) impostare i numeri di telefono inclusi negli inviti alla riunione degli utenti dell'organizzazione

Per modificare il set di numeri di telefono inclusi negli inviti alla riunione degli utenti è la propria organizzazione, vedere [impostare i numeri di telefono inclusi negli inviti in Microsoft teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Funzionalità di conferenza audio non supportate in servizi di audioconferenza con routing diretto per GCC High e DoD

Di seguito sono riportate funzionalità di conferenza audio non supportate in servizi di audioconferenza con routing diretto per GCC High e DoD:

- Notifiche di entrata e uscita tramite registrazione nomi. Per i servizi di audioconferenza con routing diretto, le notifiche di entrata e uscita vengono riprodotte nella riunione come toni.

- Criteri di restrizione delle chiamate in uscita per i servizi di audioconferenza. I controlli a livello utente per limitare le chiamate in uscita non sono applicabili alle chiamate di chiamata in uscita per le riunioni instradate tramite routing diretto.

- Disabilitare l'uso di numeri verdi per l'organizzatore di riunioni specifico. I controlli a livello di utente per limitare l'uso di numeri verdi per partecipare alle riunioni dell'organizzazione non sono applicabili alle chiamate instradate tramite routing diretto.

- Invio di messaggi di notifica agli utenti quando cambiano le impostazioni. I messaggi di notifica per i servizi di audioconferenza non sono supportati per le conferenze audio con routing diretto per GCC High e DoD.
