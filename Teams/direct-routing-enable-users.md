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
description: Informazioni su come abilitare microsoft Phone System Direct Routing agli utenti.
ms.openlocfilehash: 858b9073106945d414c2dbe56a16e6cecd104ee7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122220"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Abilitare gli utenti per routing diretto, segreteria telefonica e segreteria telefonica

Questo articolo descrive come abilitare gli utenti per Il routing diretto del sistema telefonico.  Questo è il passaggio 2 della procedura seguente per la configurazione del routing diretto:

- Passaggio 1. [Connettere SBC a Microsoft Phone System e convalidare la connessione](direct-routing-connect-the-sbc.md) 
- **Passaggio 2. Abilitare gli utenti per routing diretto, segreteria telefonica**   e segreteria telefonica (questo articolo)
- Passaggio 3. [Configurare il routing vocale](direct-routing-voice-routing.md)
- Passaggio 4. [Tradurre i numeri in un formato alternativo](direct-routing-translate-numbers.md) 


Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare il routing diretto.](direct-routing-configure.md)

Quando si è pronti per abilitare gli utenti per il routing diretto, seguire questa procedura: 

1. Creare un utente in Microsoft 365 o Office 365 e assegnare una licenza sistema telefonico. 
2. Assicurati che l'utente sia disponibile in Skype for Business online. 
3. Configurare il numero di telefono e abilitare la segreteria telefonica e la segreteria telefonica aziendale. 
4. Assegnare la modalità Solo Teams agli utenti.

## <a name="create-a-user-and-assign-the-license"></a>Creare un utente e assegnare la licenza 

Esistono due opzioni per creare un nuovo utente in Microsoft 365 o Office 365. Tuttavia, Microsoft consiglia all'organizzazione di scegliere un'opzione per evitare problemi di routing: 

- Creare l'utente in Active Directory locale e sincronizzare l'utente con il cloud. Vedere [Integrare le directory locali con Azure Active Directory.](/azure/active-directory/connect/active-directory-aadconnect)
- Creare l'utente direttamente nell'interfaccia di amministrazione di Microsoft 365. Vedere [Aggiungere utenti singolarmente o in blocco a Microsoft 365 o Office 365 - Guida per gli amministratori.](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec) 

Se la distribuzione di Skype for Business Online coesiste con Skype for Business 2015 o Lync 2010 o 2013 locale, l'unica opzione supportata è creare l'utente in Active Directory locale e sincronizzare l'utente con il cloud (opzione 1). 

Per informazioni sui requisiti di licenza, vedere [licenze e altri requisiti](direct-routing-plan.md#licensing-and-other-requirements) in Pianificare il routing [diretto.](direct-routing-plan.md)

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>Assicurarsi che l'utente sia ospitata online e che il numero di telefono non venga sincronizzato da locale (applicabile per Skype for Business Server VoIP aziendale ha abilitato la migrazione degli utenti a Teams Direct Routing)

Il routing diretto richiede che l'utente sia ospitato online. È possibile verificare esaminando il parametro RegistrarPool, che deve avere un valore nel infra.lync.com dominio. Anche il parametro OnPremLineUriManuallySet deve essere impostato su True. Questo risultato si ottiene configurando il numero di telefono e abilitando la segreteria telefonica aziendale tramite PowerShell di Skype for Business online.

1. Connettersi a una sessione di PowerShell di Skype for Business online.

2. Eseguire il comando: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    Se OnPremLineUriManuallySet è impostato su False e LineUri viene popolato con un numero di telefono <E.164>, pulire i parametri usando Skype for Business Management Shell locale prima di configurare il numero di telefono usando PowerShell di Skype for Business online. 

1. Da Skype for Business Management Shell emettere il comando: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   Dopo la sincronizzazione delle modifiche con Office 365, l'output previsto di `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` sarebbe:

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Configurare il numero di telefono e abilitare la segreteria telefonica e la segreteria telefonica aziendale 

Dopo aver creato l'utente e aver assegnato una licenza, il passaggio successivo consiste nel configurare il numero di telefono e la segreteria telefonica dell'utente. 

Per aggiungere il numero di telefono e abilitare la segreteria telefonica:
 
1. Connettersi a una sessione di PowerShell di Skype for Business online. 

2. Eseguire il comando: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    Ad esempio, per aggiungere un numero di telefono per l'utente "Spencer Low", immettere quanto segue: 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    Se gli utenti "Spencer Low" e "Stacy Quinn" condividono lo stesso numero di base con estensioni univoche, immettere quanto segue
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    È consigliabile, ma non obbligatorio, che il numero di telefono usato sia configurato come numero di telefono E.164 completo con codice paese. È supportato per configurare i numeri di telefono con estensioni che verranno usate per cercare gli utenti quando la ricerca rispetto al numero di base restituisce più di un risultato. In questo modo le aziende possono configurare i numeri di telefono con lo stesso numero di base ed estensioni univoche. Per eseguire correttamente la ricerca, l'invito deve includere il numero completo con l'interno nel modo seguente:
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > Se il numero di telefono dell'utente è gestito in locale, usare Skype for Business Management Shell locale o il Pannello di controllo per configurare il numero di telefono dell'utente. 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>Configurazione dell'invio di chiamate direttamente alla segreteria telefonica

Instradamento diretto consente di terminare la chiamata a un utente e inviarla direttamente alla segreteria telefonica dell'utente. Se si vuole inviare la chiamata direttamente alla segreteria telefonica, allegare opaque=app:voicemail all'intestazione Request URI. Ad esempio, "sip:user@yourdomain.com;opaque=app:voicemail". In questo caso, l'utente di Teams non riceverà la notifica di chiamata, la chiamata verrà connessa direttamente alla segreteria telefonica dell'utente.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Assegnare la modalità Solo Teams agli utenti per garantire che le chiamate siano atterrate in Microsoft Teams

Instradamento diretto richiede che gli utenti siano in modalità Solo Teams per garantire che le chiamate in arrivo atterrano nel client di Teams. Per impostare gli utenti in modalità Solo Teams, assegnare loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy. Per altre informazioni, vedere [Strategie di aggiornamento per gli amministratori IT.](upgrade-to-teams-on-prem-implement.md) Se l'organizzazione usa Skype for Business Server o Skype for Business online, vedere l'articolo seguente per informazioni sull'interoperabilità tra Skype e Teams: Migrazione e [interoperabilità con Skype for Business.](migration-interop-guidance-for-teams-with-skype.md)

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)