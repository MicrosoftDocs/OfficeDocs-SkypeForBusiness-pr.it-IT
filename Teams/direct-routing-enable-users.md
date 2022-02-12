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
description: Informazioni su come abilitare gli utenti per Microsoft Teams Telefono routing diretto.
ms.openlocfilehash: 4acf18799060d6cc89e477109e916b5bf0d8401a
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763331"
---
# <a name="enable-users-for-direct-routing"></a>Abilitare gli utenti per il routing diretto

Questo articolo descrive come abilitare gli utenti per il routing diretto. Questo è il passaggio 2 della procedura seguente per la configurazione del routing diretto:

- Passaggio 1. [Connessione SBC con Sistema telefonico e convalidare la connessione](direct-routing-connect-the-sbc.md) 
- **Passaggio 2. Abilitare gli utenti per il routing diretto**   (questo articolo)
- Passaggio 3. [Configurare il routing vocale](direct-routing-voice-routing.md)
- Passaggio 4. [Tradurre i numeri in un formato alternativo](direct-routing-translate-numbers.md) 


Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare il routing diretto](direct-routing-configure.md).

Quando si è pronti per abilitare gli utenti per il routing diretto, seguire questa procedura: 

1. Creare un utente in Microsoft 365 e assegnare una Sistema telefonico licenza.  
2. Verificare che l'utente sia disponibile online.
3. Configurare il numero di telefono e abilitare voIP aziendale. 
4. Assegnare Teams solo agli utenti.

## <a name="create-a-user-and-assign-the-license"></a>Creare un utente e assegnare la licenza

Sono disponibili due opzioni per creare un nuovo utente in Microsoft 365. Tuttavia, Microsoft consiglia all'organizzazione di scegliere un'opzione per evitare problemi di routing: 

- Creare l'utente in Active Directory locale e sincronizzare l'utente con il cloud. Vedere [Integrare le directory locali con Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).
- Creare l'utente direttamente nel interfaccia di amministrazione di Microsoft 365. Vedere [Aggiungere utenti singolarmente o in blocco a Microsoft 365 o Office 365 - Guida per gli amministratori](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Se la distribuzione di Skype for Business Online coesiste con Skype for Business 2015 o Lync 2010 o 2013 locale, l'unica opzione supportata è creare l'utente in Active Directory locale e sincronizzare l'utente con il cloud (opzione 1). 

Per informazioni sui requisiti di licenza, vedere licenze [e altri requisiti](direct-routing-plan.md#licensing-and-other-requirements) in [Pianificare il routing diretto](direct-routing-plan.md).

## <a name="ensure-that-the-user-is-homed-online"></a>Verificare che l'utente sia disponibile online 

Questo passaggio si applica Skype for Business Server VoIP aziendale utenti abilitati per la migrazione a Teams routing diretto.

Il routing diretto richiede che l'utente sia ospitato online. È possibile verificare esaminando il parametro RegistrarPool, che deve avere un valore nel infra.lync.com dominio. Microsoft consiglia, ma non richiede, di modificare lineuri da locale a online durante la migrazione degli utenti a Teams Direct Routing. 

1. Connessione una Microsoft Teams di PowerShell.

2. Eseguire il comando: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    Se OnPremLineUriManuallySet è impostato su False e LineUri viene popolato con un numero di telefono <E.164>, il numero di telefono è stato assegnato in locale e sincronizzato con Microsoft 365. Se si vuole gestire il numero di telefono online, pulire il parametro usando Skype for Business Management Shell locale e eseguire la sincronizzazione con Microsoft 365 prima di configurare il numero di telefono usando Teams PowerShell. 

1. Da Skype for Business Management Shell, eseguire il comando: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > Non impostare EnterpriseVoiceEnabled su False perché non è necessario farlo e ciò può causare problemi di normalizzazione del piano di chiamata se sono in uso telefoni Skype for Business legacy e la configurazione ibrida tenant è impostata con UseOnPremDialPlan $True. 
    
   Dopo la sincronizzazione delle modifiche con Microsoft 365 l'output previsto di `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` sarebbe:

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > Tutti gli attributi del telefono dell'utente devono essere gestiti online prima di disaccontire l'ambiente Skype for Business [locale](/skypeforbusiness/hybrid/decommission-on-prem-overview). 

## <a name="configure-the-phone-number-and-enable-enterprise-voice"></a>Configurare il numero di telefono e abilitare voIP aziendale 

Dopo aver creato l'utente e aver assegnato una licenza, è necessario configurare le impostazioni del telefono online dell'utente. Si noti che la configurazione di Cloud Voicemail per l'utente è automatica. Non è necessario eseguire altre operazioni di configurazione.

1. Connessione a una Microsoft Teams di PowerShell. 

2. I passaggi successivi variano a seconda che si gestirà il numero di telefono dell'utente in locale o online. Se si gestisce il numero di telefono locale, è necessario usare la shell di gestione locale di Skype for Business Management Shell, il Pannello di controllo o uno dei metodi descritti in Decidere come gestire gli attributi dopo la [decommisione](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes).

   - Se si gestisce il numero di telefono dell'utente in locale, è necessario assicurarsi che l'utente sia abilitato VoIP aziendale online usando il comando seguente:

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -EnterpriseVoiceEnabled $true
       ```
       
   - Se si gestisce il numero di telefono dell'utente online, è necessario assegnare il numero di telefono all'utente usando il comando seguente in Teams PowerShell. L'utente viene VoIP aziendale abilitato automaticamente dal comando: 
 
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -PhoneNumber <phone number> -PhoneNumberType DirectRouting
       ```
    
       Ad esempio, per aggiungere un numero di telefono per l'utente "Spencer Low", immettere quanto segue: 

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388797" -PhoneNumberType DirectRouting
       ```
       Se gli utenti "Spencer Low" e "Stacy Quinn" condividono lo stesso numero di base con estensioni univoche, immettere quanto segue
    
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388701;ext=1001" -PhoneNumberType DirectRouting
       Set-CsPhoneNumberAssignment -Identity "stacy.quinn@contoso.com" -PhoneNumber "+14255388701;ext=1002" -PhoneNumberType DirectRouting
       ```

    Microsoft consiglia, ma non richiede, che il numero di telefono sia configurato come numero di telefono E.164 completo con codice paese. È possibile configurare i numeri di telefono con le estensioni. Queste estensioni verranno usate per cercare gli utenti quando la ricerca sul numero di base restituisce più di un risultato. Questa funzionalità consente alle aziende di configurare i numeri di telefono con lo stesso numero di base ed estensioni univoche. Per eseguire correttamente la ricerca, l'invito deve includere il numero completo con l'interno nel modo seguente:
    
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```


## <a name="configure-sending-calls-directly-to-voicemail"></a>Configurare l'invio di chiamate direttamente alla segreteria telefonica

Instradamento diretto consente di terminare la chiamata a un utente e inviarla direttamente alla segreteria telefonica dell'utente. Se si vuole inviare la chiamata direttamente alla segreteria telefonica, allegare opaque=app:voicemail all'intestazione Request URI. Ad esempio, "sip:user@yourdomain.com;opaque=app:voicemail". L Teams'utente non riceverà la notifica di chiamata, la chiamata verrà connessa direttamente alla segreteria telefonica dell'utente.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Assegnare Teams solo agli utenti per garantire che le chiamate siano Microsoft Teams

Instradamento diretto richiede che gli utenti siano in Teams solo per garantire che le chiamate in arrivo atterrano nel client Teams messaggi. Per mettere gli utenti in Teams solo utenti, assegnare loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy. Per altre informazioni, vedere [Strategie di aggiornamento per gli amministratori IT](upgrade-to-teams-on-prem-implement.md). Se l'organizzazione usa Skype for Business Server, vedere l'articolo seguente per informazioni sull'interoperabilità tra Skype e [Teams: Migrazione](migration-interop-guidance-for-teams-with-skype.md) e interoperabilità con Skype for Business.

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
