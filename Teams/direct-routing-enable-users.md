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
description: Informazioni su come abilitare gli utenti al routing diretto di Microsoft Phone System.
ms.openlocfilehash: 5739797649c639e3259c6972da665ae0ced4b4bf
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655483"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Abilitare gli utenti per il routing diretto, la voce e la segreteria telefonica

Questo articolo descrive come abilitare gli utenti per il routing diretto del sistema telefonico.  Questo è il passaggio 2 dei passaggi seguenti per la configurazione del routing diretto:

- Passaggio 1. [Connettere il SBC con il sistema telefonico Microsoft e convalidare la connessione](direct-routing-connect-the-sbc.md) 
- **Passaggio 2. Abilitare gli utenti per il routing diretto, la voce e la segreteria telefonica**   (questo articolo)
- Passaggio 3. [Configurare il routing vocale](direct-routing-voice-routing.md)
- Passaggio 4. [Tradurre i numeri in un formato alternativo](direct-routing-translate-numbers.md) 


Per informazioni su tutti i passaggi necessari per la configurazione del routing diretto, vedere [configurare il routing diretto](direct-routing-configure.md).

Quando si è pronti per consentire agli utenti di eseguire il routing diretto, seguire questa procedura: 

1. Creare un utente in Microsoft 365 o Office 365 e assegnare una licenza per il sistema telefonico. 
2. Verificare che l'utente sia ospitato in Skype for business online. 
3. Configurare il numero di telefono e abilitare VoIP aziendale e segreteria telefonica. 
4. Assegnare la modalità solo teams agli utenti.

## <a name="create-a-user-and-assign-the-license"></a>Creare un utente e assegnare la licenza 

Sono disponibili due opzioni per la creazione di un nuovo utente in Microsoft 365 o Office 365. Tuttavia, Microsoft consiglia all'organizzazione di scegliere un'opzione per evitare problemi di routing: 

- Creare l'utente in Active Directory locale e sincronizzare l'utente con il cloud. Vedere [integrare le directory locali con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
- Creare l'utente direttamente nell'interfaccia di amministrazione di Microsoft 365. Vedere [aggiungere utenti singolarmente o in blocco a Microsoft 365 o Office 365-Guida per gli amministratori](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Se la distribuzione di Skype for business online è coesistente con Skype for business 2015 o Lync 2010 o 2013 in locale, l'unica opzione supportata consiste nel creare l'utente nell'Active Directory locale e sincronizzare l'utente con il cloud (opzione 1). 

Per informazioni sui requisiti di licenza, vedere [licenze e altri requisiti](direct-routing-plan.md#licensing-and-other-requirements) per [pianificare il routing diretto](direct-routing-plan.md).

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>Verificare che l'utente sia ospitato online e che il numero di telefono non venga sincronizzato da locale (applicabile per gli utenti abilitati per Skype for Business Server Enterprise Voice che vengono migrati in routing Direct Teams)

Il routing diretto richiede che l'utente sia ospitato online. Puoi controllare osservando il parametro RegistrarPool, che deve avere un valore nel dominio infra.lync.com. Anche il parametro OnPremLineUriManuallySet deve essere impostato su true. Questa operazione viene eseguita configurando il numero di telefono e abilitando VoIP aziendale e segreteria telefonica con PowerShell per Skype for business online.

1. Connettere una sessione di PowerShell di Skype for business online.

2. Emettere il comando: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    Nel caso in cui OnPremLineUriManuallySet sia impostato su false e LineUri venga compilato con un numero di telefono <E. 164>, è necessario pulire i parametri usando Skype for Business Management Shell locale, prima di configurare il numero di telefono usando PowerShell per Skype for business online. 

1. Da Skype for Business Management Shell emettere il comando: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   Dopo che le modifiche sono state sincronizzate con Office 365, l'output previsto `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` sarà:

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Configurare il numero di telefono e abilitare VoIP aziendale e segreteria telefonica 

Dopo aver creato l'utente e assegnato una licenza, il passaggio successivo consiste nel configurare il numero di telefono e la segreteria telefonica dell'utente. 

Per aggiungere il numero di telefono e abilitare per la segreteria telefonica:
 
1. Connettere una sessione di PowerShell di Skype for business online. 

2. Emettere il comando: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    Ad esempio, per aggiungere un numero di telefono per l'utente "Spencer low", immettere quanto segue: 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    Se gli utenti "Spencer low" e "Stacy Quinn" condividono lo stesso numero di base con estensioni univoche, immettere quanto segue
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    È consigliabile, ma non necessario, che il numero di telefono usato sia configurato come numero di telefono E. 164 completo con prefisso nazionale. È supportato per configurare i numeri di telefono con le estensioni che verranno usate per cercare gli utenti quando la ricerca rispetto al numero di base restituisce più risultati. Questo consente alle aziende di configurare i numeri di telefono con lo stesso numero di base e le estensioni esclusive. Affinché la ricerca abbia successo, l'invito deve includere il numero intero con estensione come indicato di seguito:
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > Se il numero di telefono dell'utente viene gestito in locale, USA Skype for Business Management Shell locale o pannello di controllo per configurare il numero di telefono dell'utente. 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>Configurazione dell'invio di chiamate direttamente alla segreteria telefonica

Il routing diretto consente di terminare la chiamata a un utente e di inviarla direttamente alla segreteria telefonica dell'utente. Se si vuole inviare la chiamata direttamente alla segreteria telefonica, allegare opaque = app: voicemail all'intestazione dell'URI della richiesta. Ad esempio, "SIP: user@yourdomain. com; opaque = app: voicemail". In questo caso, l'utente teams non riceverà la notifica chiamante, la chiamata verrà connessa direttamente alla segreteria telefonica dell'utente.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Assegnare la modalità solo team agli utenti per garantire la destinazione delle chiamate in Microsoft Teams

Il routing diretto richiede che gli utenti siano in modalità solo teams per garantire la terra delle chiamate in arrivo nel client teams. Per inserire gli utenti solo in modalità teams, assegna loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy. Per altre informazioni, vedere [aggiornare le indicazioni per gli amministratori it](upgrade-to-teams-on-prem-overview.md). Se l'organizzazione usa Skype for Business Server o Skype for business online, vedere l'articolo seguente per informazioni sull'interoperabilità tra Skype e teams: [migrazione e interoperabilità con Skype for business](migration-interop-guidance-for-teams-with-skype.md).

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
