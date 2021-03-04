---
title: Abilitare gli utenti per il routing diretto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Scopri come abilitare l'instradamento diretto del Sistema telefonico Microsoft.
ms.openlocfilehash: 972bd8d5e01a050a67978560b8de272439fda40d
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421311"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Abilitare gli utenti per l'instradamento diretto, la voce e la segreteria telefonica

Questo articolo descrive come abilitare gli utenti per l'instradamento diretto del sistema telefonico.  Questo è il passaggio 2 della procedura seguente per la configurazione del routing diretto:

- Passaggio 1. [Collegare il servizio SBC al Sistema telefonico Microsoft e convalidare la connessione](direct-routing-connect-the-sbc.md) 
- **Passaggio 2. Abilitare gli utenti per l'instradamento diretto, la voce e la segreteria**   telefonica (questo articolo)
- Passaggio 3. [Configurare il routing vocale](direct-routing-voice-routing.md)
- Passaggio 4. [Convertire i numeri in un formato alternativo](direct-routing-translate-numbers.md) 


Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare l'instradamento diretto.](direct-routing-configure.md)

Quando si è pronti ad abilitare gli utenti per il routing diretto, seguire questa procedura: 

1. Creare un utente in Microsoft 365 o Office 365 e assegnare una licenza Sistema telefonico. 
2. Assicurarsi che l'utente sia disponibile in Skype for Business online. 
3. Configura il numero di telefono e abilita la segreteria telefonica aziendale. 
4. Assegnare la modalità Solo Teams agli utenti.

## <a name="create-a-user-and-assign-the-license"></a>Creare un utente e assegnare la licenza 

Sono disponibili due opzioni per creare un nuovo utente in Microsoft 365 o Office 365. Tuttavia, Microsoft consiglia all'organizzazione di scegliere una delle opzioni per evitare problemi di routing: 

- Creare l'utente in Active Directory locale e sincronizzare l'utente con il cloud. Vedere [Integrare le directory locali con Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- Creare l'utente direttamente nell'interfaccia di amministrazione di Microsoft 365. Vedere [Aggiungere utenti singolarmente o in blocco a Microsoft 365 o Office 365 - Guida per l'amministratore.](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec) 

Se la distribuzione di Skype for Business online coesiste con Skype for Business 2015 o Lync 2010 o 2013 locale, l'unica opzione supportata è creare l'utente nella distribuzione locale di Active Directory e sincronizzare l'utente con il cloud (opzione 1). 

Per informazioni sui requisiti di licenza, vedere [licenze e altri requisiti](direct-routing-plan.md#licensing-and-other-requirements) in Pianificare il routing [diretto.](direct-routing-plan.md)

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>Assicurarsi che l'utente sia ospitata online e che il numero di telefono non venga sincronizzato dalla distribuzione locale (applicabile per gli utenti abilitati per Skype for Business Server VoIP aziendale in fase di migrazione a Routing diretto di Teams)

L'instradamento diretto richiede che l'utente sia ospitata online. È possibile verificare esaminando il parametro RegistrarPool, che deve avere un valore nel infra.lync.com dominio. Anche il parametro OnPremLineUriManuallySet deve essere impostato su True. Questa operazione si ottiene configurando il numero di telefono e abilitando la segreteria telefonica e la voce aziendale con PowerShell di Skype for Business Online.

1. Connettere una sessione di PowerShell di Skype for Business online.

2. Eseguire il comando: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    Se OnPremLineUriManuallySet è impostato su False e LineUri viene popolato con un> di numero di telefono <E.164, pulisci i parametri usando Skype for Business Management Shell locale prima di configurare il numero di telefono con PowerShell di Skype for Business online. 

1. Da Skype for Business Management Shell emettere il comando: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   Dopo la sincronizzazione delle modifiche con Office 365, l'output previsto `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` sarà:

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Configurare il numero di telefono e abilitare voIP aziendale e segreteria telefonica 

Dopo aver creato l'utente e aver assegnato una licenza, il passaggio successivo consiste nel configurare il numero di telefono e la casella vocale dell'utente. 

Per aggiungere il numero di telefono e abilitare la segreteria telefonica:
 
1. Connettere una sessione di PowerShell di Skype for Business online. 

2. Eseguire il comando: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    Ad esempio, per aggiungere un numero di telefono per l'utente "In basso", immettere quanto segue: 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    Se gli utenti "Low" e "Stacy Quinn" condividono lo stesso numero di base con estensioni univoche, immetti quanto segue:
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    È consigliabile, ma non obbligatorio, che il numero di telefono utilizzato sia configurato come numero di telefono E.164 completo con codice paese. È supportato per configurare i numeri di telefono con estensioni che verranno usate per cercare gli utenti quando la ricerca rispetto al numero di base restituisce più di un risultato. In questo modo le aziende possono configurare i numeri di telefono con lo stesso numero di base e estensioni univoche. Per eseguire correttamente la ricerca, l'invito deve includere il numero completo con l'interno nel modo seguente:
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > Se il numero di telefono dell'utente è gestito in locale, usare la versione locale di Skype for Business Management Shell o il Pannello di controllo per configurare il numero di telefono dell'utente. 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>Configurazione dell'invio di chiamate direttamente alla segreteria telefonica

L'instradamento diretto consente di terminare la chiamata a un utente e inviarla direttamente alla segreteria telefonica dell'utente. Se desideri inviare la chiamata direttamente alla segreteria telefonica, allega opaque=app:voicemail all'intestazione dell'URI di richiesta. Ad esempio, "sip:user@yourdomain.com;opaque=app:voicemail". In questo caso, l'utente di Teams non riceverà la notifica di chiamata, la chiamata sarà collegata direttamente alla segreteria telefonica dell'utente.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Assegnare la modalità Solo Teams agli utenti per assicurarsi che le chiamate siano disponibili in Microsoft Teams

L'instradamento diretto richiede che gli utenti siano in modalità Solo teams per fare in modo che le chiamate in arrivo siano sul client di Teams. Per impostare gli utenti in modalità Solo teams, assegnare loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy. Per altre informazioni, vedere Le [strategie di aggiornamento per gli amministratori IT.](upgrade-to-teams-on-prem-implement.md) Se la tua organizzazione utilizza Skype for Business Server o Skype for Business online, consulta il seguente articolo sull'interoperabilità tra Skype e Teams: Migrazione e interoperabilità con [Skype for Business.](migration-interop-guidance-for-teams-with-skype.md)

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
