---
title: Abilitare gli utenti per il routing diretto
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come abilitare gli utenti per Telefono di Microsoft Teams Direct Routing.
ms.openlocfilehash: edf02077bf5c15da56fe7894d1faec2a9b87b0d5
ms.sourcegitcommit: 9968ef7d58c526e35cb58174db3535fd6b2bd1db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/09/2022
ms.locfileid: "65284081"
---
# <a name="enable-users-for-direct-routing"></a>Abilitare gli utenti per il routing diretto

Questo articolo descrive come abilitare gli utenti per il routing diretto. Questo è il passaggio 2 della procedura seguente per la configurazione del routing diretto:

- Passaggio 1. [Connessione la scheda SBC con Sistema telefonico e convalidare la connessione](direct-routing-connect-the-sbc.md) 
- **Passaggio 2. Abilitare gli utenti per il routing diretto**   (questo articolo)
- Passaggio 3. [Configurare il routing vocale](direct-routing-voice-routing.md)
- Passaggio 4. [Tradurre numeri in un formato alternativo](direct-routing-translate-numbers.md) 


Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare il routing diretto](direct-routing-configure.md).

Quando si è pronti per abilitare gli utenti per il routing diretto, seguire questa procedura: 

1. Creare un utente in Microsoft 365 e assegnare una licenza di Sistema telefonico.  
2. Assicurati che l'utente sia ospitato online.
3. Configura il numero di telefono e abilita voIP aziendale. 
4. Assegnare Teams modalità Solo agli utenti.

## <a name="create-a-user-and-assign-the-license"></a>Creare un utente e assegnare la licenza

Sono disponibili due opzioni per creare un nuovo utente in Microsoft 365. Tuttavia, Microsoft consiglia all'organizzazione di scegliere un'opzione per evitare problemi di routing: 

- Creare l'utente in Active Directory locale e sincronizzarlo con il cloud. Vedere [Integrare le directory locali con Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).
- Creare l'utente direttamente nel interfaccia di amministrazione di Microsoft 365. Vedere [Aggiungere utenti singolarmente o in blocco a Microsoft 365 o Office 365 - Guida per l'amministratore](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Se la distribuzione di Skype for Business Online convive con Skype for Business 2015 o Lync 2010 o 2013 locale, l'unica opzione supportata consiste nel creare l'utente nel Active Directory locale e sincronizzare l'utente con il cloud (opzione 1). 

Per informazioni sui requisiti di licenza, vedere [licenze e altri requisiti](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).

## <a name="ensure-that-the-user-is-homed-online"></a>Assicurarsi che l'utente sia ospitato online 

Questo passaggio si applica agli utenti abilitati Skype for Business Server VoIP aziendale di cui viene eseguita la migrazione a Teams routing diretto.

Il routing diretto richiede che l'utente sia ospitato online. Per verificarlo, esaminare il parametro RegistrarPool, che deve avere un valore nel dominio infra.lync.com. Microsoft consiglia, ma non richiede, di modificare LineURI da locale a online durante la migrazione degli utenti a Teams Direct Routing. 

1. Connessione una sessione di PowerShell Microsoft Teams.

2. Esegui il comando: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri
    ``` 
    Se SuPremLineUri viene popolato con un numero di telefono <E.164>, il numero di telefono è stato assegnato in locale e sincronizzato con Microsoft 365. Se si vuole gestire il numero di telefono online, cancellare il parametro usando Skype for Business Management Shell locale e sincronizzarlo con Microsoft 365 prima di configurare il numero di telefono con Teams PowerShell. 

1. Da Skype for Business Management Shell, eseguire il comando: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > Non impostare EnterpriseVoiceEnabled su False perché non è necessario farlo e ciò può causare problemi di normalizzazione del piano di chiamata se sono in uso telefoni Skype for Business legacy e la configurazione ibrida del tenant è impostata con UseOnPremDialPlan $True. 
    
   Dopo la sincronizzazione delle modifiche con Microsoft 365, l'output previsto di `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri` è:

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > Tutti gli attributi del telefono dell'utente devono essere gestiti online prima di [decodificare l'ambiente Skype for Business locale](/skypeforbusiness/hybrid/decommission-on-prem-overview). 

## <a name="configure-the-phone-number-and-enable-enterprise-voice"></a>Configurare il numero di telefono e abilitare voIP aziendale 

Dopo aver creato l'utente e assegnato una licenza, è necessario configurare le impostazioni del telefono online dell'utente. La configurazione di Cloud Voicemail per l'utente è automatica e non è necessario eseguire altre configurazioni.

È possibile configurare il numero di telefono usando l'interfaccia di amministrazione di Teams o Teams PowerShell.

### <a name="use-teams-admin-center"></a>Usare Teams'interfaccia di amministrazione

1. Passare a **UtentiGesti** ->  **gli utenti**.

2. Selezionare un utente.

2. In **Informazioni generali** **account** selezionare **Modifica**.

3. In **Assegna numero di telefono** seleziona **Routing diretto** dal menu a discesa **tipo di numero Telefono**.

4. Se applicabile, immetti un numero di telefono assegnato e un numero di telefono.

5. Selezionare **Applica.**

Le informazioni generali dell'account ora mostrano il numero di telefono assegnato e l'instradamento diretto come tipo di numero di telefono.


### <a name="use-powershell"></a>Usare PowerShell

1. Connessione a una sessione di PowerShell Microsoft Teams. 

2. I passaggi successivi dipendono dalla gestione del numero di telefono dell'utente in locale o online. Se si gestisce il numero di telefono in locale, è necessario usare Skype for Business Management Shell locale, Pannello di controllo o uno dei metodi descritti in [Decidere come gestire gli attributi dopo la rimozione](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes).

   - Se si gestisce il numero di telefono dell'utente in locale, è necessario assicurarsi che l'utente sia VoIP aziendale abilitato online usando il comando seguente:

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -EnterpriseVoiceEnabled $true
       ```
       
   - Se gestisci il numero di telefono dell'utente online, devi assegnare il numero di telefono all'utente usando il comando seguente in Teams PowerShell. L'utente viene automaticamente VoIP aziendale abilitato dal comando: 
 
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -PhoneNumber <phone number> -PhoneNumberType DirectRouting
       ```
    
       Ad esempio, per aggiungere un numero di telefono per l'utente "Spencer Low", immettere quanto segue: 

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388797" -PhoneNumberType DirectRouting
       ```
       Se gli utenti "Spencer Low" e "Stacy Quinn" condividono lo stesso numero di base con estensioni univoche, immettere le seguenti
    
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388701;ext=1001" -PhoneNumberType DirectRouting
       Set-CsPhoneNumberAssignment -Identity "stacy.quinn@contoso.com" -PhoneNumber "+14255388701;ext=1002" -PhoneNumberType DirectRouting
       ```

    Microsoft consiglia, ma non richiede, che il numero di telefono sia configurato come numero di telefono E.164 completo con codice paese. Puoi configurare i numeri di telefono con le estensioni. Queste estensioni verranno usate per cercare gli utenti quando la ricerca del numero di base restituisce più di un risultato. Questa funzionalità consente alle aziende di configurare i numeri di telefono con lo stesso numero di base ed estensioni univoche. Affinché la ricerca venga eseguita correttamente, l'invito deve includere il numero completo con estensione come indicato di seguito:
    
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```


## <a name="configure-sending-calls-directly-to-voicemail"></a>Configurare l'invio di chiamate direttamente alla segreteria telefonica

Direct Routing consente di terminare la chiamata a un utente e inviarla direttamente alla segreteria telefonica dell'utente. Se si vuole inviare la chiamata direttamente alla segreteria telefonica, allegare opaque=app:voicemail all'intestazione URI richiesta. Ad esempio, "sip:user@yourdomain.com;opaque=app:voicemail". L Teams utente non riceverà la notifica di chiamata. La chiamata verrà invece collegata direttamente alla segreteria telefonica dell'utente.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Assegnare Teams modalità Solo agli utenti per assicurarsi che le chiamate atterrano in Microsoft Teams

Il routing diretto richiede che gli utenti siano in modalità solo Teams per garantire che le chiamate in arrivo atterrano nel client Teams. Per mettere gli utenti in modalità solo Teams, assegnare loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy. Per altre informazioni, vedere [Strategie di aggiornamento per gli amministratori IT](upgrade-to-teams-on-prem-implement.md). Se l'organizzazione usa Skype for Business Server, vedere l'articolo seguente per informazioni sull'interoperabilità tra Skype e Teams: [migrazione e interoperabilità con Skype for Business](migration-interop-guidance-for-teams-with-skype.md).

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
