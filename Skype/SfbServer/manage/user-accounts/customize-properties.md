---
title: Personalizzare le proprietà degli account utente per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: È possibile usare le procedure descritte in questa sezione per modificare le singole proprietà degli account utente.
ms.openlocfilehash: eca88717d0b81ddd7c27fc140df9bdbf7590c5c6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991431"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Personalizzare le proprietà degli account utente per Skype for Business Server
 
È possibile usare le procedure descritte in questa sezione per modificare le singole proprietà degli account utente.
  
Esistono due operazioni di base che è possibile eseguire a livello di singolo utente:
  
- [Configurare le opzioni di telefonia per un account utente specifico](customize-properties.md#Tel_Op)
    
- [Trasferire gli utenti in un altro pool](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Configurare le opzioni di telefonia per un account utente specifico
<a name="Tel_Op"> </a>

È possibile personalizzare le impostazioni di telefonia per un utente specifico, purché il singolo utente sia stato abilitato per Skype for Business Server e l'organizzazione supporti la telefonia.
  
Le opzioni di telefonia degli utenti di Skype for Business Server includono le seguenti:
  
- **Disattivato audio/video** L'utente non può effettuare chiamate con audio e video.
    
- **Solo da PC a PC** L'utente può effettuare solo chiamate audio o video da PC a PC.
    
- **Enterprise Voice** L'utente può usare l'infrastruttura di Skype for Business Server per instradare tutte le chiamate in entrata e in uscita. L'utente può anche effettuare chiamate da PC a PC.
    
- **Controllo delle chiamate remote** L'utente può usare Skype for Business Server per controllare il telefono desktop e può anche effettuare chiamate da PC a PC.
    
Per informazioni dettagliate sulla configurazione della telefonia per un'organizzazione, vedere [abilitare gli utenti di VoIP aziendale in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) e [distribuire VoIP aziendale in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) nella documentazione relativa alla distribuzione.
  
1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **utenti**.
    
4. Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente desiderato, quindi fare clic su **trova**.
    
5. Nella tabella fare clic sull'account utente che si vuole modificare.
    
6. Nel menu **modifica** fare clic su **modifica**.
    
7. In **telefonia**eseguire le operazioni seguenti:
    
   - Per disabilitare le chiamate audio e video per l'utente, fare clic su **disabilitato audio/video**.
    
   - Per abilitare le comunicazioni audio da PC a PC per l'utente, ma non per controllo delle chiamate remote o VoIP aziendale, fare clic su **solo da PC a PC**. Specificare un valore per l' **URI di linea** per il telefono usato dall'utente per le comunicazioni audio da PC a PC.
    
   - Per instradare le telefonate dell'utente usando l'infrastruttura Skype for business in conformità con la classe di criteri di servizio, incluse le comunicazioni audio da PC a PC, fai clic su **VoIP aziendale**. In **URI linea**specificare il numero di telefono per VoIP aziendale. In **criteri di dial plan** e **criteri vocali**specificare i criteri appropriati per l'utente. Per specificare le regole di normalizzazione per la traduzione dei numeri di telefono comunicati dall'utente nel formato E. 164, selezionare il profilo di posizione appropriato in **criteri posizione**.
    
   - Per abilitare il controllo delle chiamate remote, che consente agli utenti di controllare la linea telefonica desktop da Skype for Business Server per effettuare chiamate da PC a PC e chiamate da PC a telefono, fare clic su **controllo chiamate remote**. In **URI linea**specificare il numero di telefono per il controllo delle chiamate remote. L'utente deve avere un telefono desktop e una connessione PBX (Private Branch Exchange) per il routing delle chiamate.
    
## <a name="move-users-to-another-pool"></a>Trasferire gli utenti in un altro pool
<a name="Move_Users"> </a>

Puoi usare il pannello di controllo di Skype for Business Server per assegnare gli utenti a un server o un pool specifico.
  
> [!TIP]
> Lo spostamento di tutti gli utenti esistenti da un pool di origine che gestisce Lync Server 2010 o versioni precedenti a un pool di destinazione di Skype for Business Server in un ambiente di Active Directory complesso può causare una replica di Active Directory più lenta. Per evitare questo problema, puoi usare i filtri di ricerca per trasferire gli utenti da pool che usano Lync Server 2010 o versioni precedenti separatamente oppure puoi usare Skype for Business Server Management Shell per trasferire gli utenti con i cmdlet. Inoltre, la funzionalità di filtro funziona con gli utenti di Skype for Business Server. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Per trasferire gli utenti selezionati in un altro server o pool

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **utenti**.
    
4. Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente desiderato, quindi fare clic su **trova**. 
    
5. Nella tabella selezionare un utente o utenti specifici nell'elenco. 
    
6. Nel menu **azione** fare clic su **Trasferisci utenti selezionati in pool**.
    
7. In **Move users**selezionare il pool in cui si vuole trasferire gli utenti nel **pool di registrar di destinazione**.
    
8. Opzionale Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **forza** .
    
    > [!CAUTION]
    > Se si seleziona **forza**, l'account utente viene spostato, ma vengono eliminati tutti i dati dell'utente associato, ad esempio le conferenze che l'utente ha programmato. Se non viene selezionato, sia l'account che i dati associati vengono spostati. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Per trasferire tutti gli utenti da un server o da un pool a un altro server o pool

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **utenti**.
    
4. Nel menu **azione** fare clic su **Trasferisci tutti gli utenti in pool**.
    
5. In **Move users**selezionare il pool che contiene gli account utente che si desidera trasferire nel **pool di registrazione di origine**.
    
6. Nel **pool di registrar di destinazione**selezionare il pool a cui si vuole trasferire gli utenti.
    
7. Opzionale Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **forza** .
    
    > [!CAUTION]
    > Se si seleziona **forza**, l'account utente viene spostato, ma vengono eliminati tutti i dati dell'utente associato, ad esempio le conferenze che l'utente ha programmato. Se non viene selezionato, sia l'account che i dati associati vengono spostati. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Per trasferire gli utenti da un pool a un altro tramite un filtro

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **utenti**.
    
4. In **ricerca utente**fare clic su **Cerca**e quindi su **Aggiungi filtro**.
    
5. Nel criterio di ricerca selezionare **pool di registrazione**, selezionare **uguale a**, selezionare **FQDN corrente del pool**e quindi fare clic su **trova**.
    
6. Nel menu **azione** fare clic su **Trasferisci tutti gli utenti in pool**.
    
    > [!NOTE]
    > Quando si applica un filtro a un set di utenti esistente, l'opzione **trasferisce tutti gli utenti al pool** si trova nel contesto del sottoinsieme filtrato degli utenti, non di **tutti** gli utenti possibili.
  
7. In **Move users**selezionare il pool che contiene gli account utente che si desidera trasferire nel **pool di registrazione di origine**.
    
8. Nel **pool di registrar di destinazione**selezionare il pool in cui si desidera trasferire gli utenti.
    
9. Opzionale Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **forza** .
    
    > [!CAUTION]
    > Se si seleziona **forza**, l'account utente viene spostato, ma vengono eliminati tutti i dati degli utenti associati, ad esempio le conferenze che l'utente ha programmato e i contatti. Se non viene selezionato, sia l'account che i dati associati vengono spostati. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Per trasferire gli utenti da un pool a un altro usando i cmdlet di Windows PowerShell

1. A seconda di come vengono eseguiti i comandi di Windows PowerShell, ovvero localmente o in remoto, è necessario accedere come membri dei ruoli amministrativi corretti di Skype for Business Server come segue:
    
   un. Se si esegue il comando nel computer locale (ad esempio, si accede direttamente a un front end Server): accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di configurazione per i **delegati**.
    
   b. Se si eseguono i comandi in remoto in un altro computer, ad esempio si accede al computer e si eseguono i comandi in remoto in un server front-end Standard Edition: da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator ruolo, accedere a qualsiasi computer della distribuzione interna.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business**e quindi su **Skype for Business Server Management Shell**.
    
3. Per trasferire singoli utenti, usare il cmdlet Move-CsUser come indicato di seguito:
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    Dove l'utente deve spostarsi è l'utente Pilar Ackerman e l'utente verrà spostato dal proprio pool di Home attualmente assegnato al pool pool01.contoso.net
    
4. Per trasferire un numero elevato di utenti, usare i filtri con il cmdlet **Get-CsUser** e passare il set di utenti risultante a **Move-CsUser**:
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    I comandi combinati di **Get-CsUser** e **Move-CsUser** possono risultare in questo:
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


