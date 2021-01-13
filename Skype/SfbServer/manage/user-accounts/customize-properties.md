---
title: Personalizzare le proprietà degli account utente per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: È possibile utilizzare le procedure descritte in questa sezione per modificare le singole proprietà degli account utente.
ms.openlocfilehash: 6f2c3a76f9047da0a5d78695518cfb8355ab82e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826266"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Personalizzare le proprietà degli account utente per Skype for Business Server
 
È possibile utilizzare le procedure descritte in questa sezione per modificare le singole proprietà degli account utente.
  
Sono disponibili due operazioni di base che possono essere eseguite a livello di singolo utente:
  
- [Configurare le opzioni di telefonia per un account utente specifico](customize-properties.md#Tel_Op)
    
- [Spostare gli utenti in un altro pool](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Configurare le opzioni di telefonia per un account utente specifico
<a name="Tel_Op"> </a>

È possibile personalizzare le impostazioni di telefonia per un utente specifico (purché il singolo utente sia stato abilitato per Skype for Business Server e l'organizzazione supporti la telefonia).
  
Le opzioni di telefonia degli utenti di Skype for Business Server includono le seguenti:
  
- **Audio/video disabilitato** L'utente non può effettuare chiamate con audio e video.
    
- **Solo da PC a PC** L'utente può effettuare solo chiamate audio o video da PC a PC.
    
- **VoIP aziendale** L'utente può utilizzare l'infrastruttura di Skype for Business Server per instradare tutte le chiamate in entrata e in uscita. Può inoltre effettuare chiamate da PC a PC.
    
- **Controllo delle chiamate remote** L'utente può usare Skype for Business Server per controllare il telefono desktop e può anche effettuare chiamate da PC a PC.
    
Per informazioni dettagliate sulla configurazione della telefonia per un'organizzazione, vedere [abilitare gli utenti per VoIP aziendale in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) e [distribuire VoIP aziendale in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) nella documentazione relativa alla distribuzione.
  
1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **Utenti**.
    
4. Nella casella **Ricerca utenti** digitare interamente o parzialmente il nome visualizzato, il nome, il cognome, il nome account del sistema degli account di sicurezza (SAM), l'indirizzo SIP o l'URI (Uniform Resource Identifier) linea dell'account utente desiderato e quindi fare clic su **Trova**.
    
5. Nella tabella fare clic sull'account utente che si desidera modificare.
    
6. Scegliere **Modifica** dal menu **Modifica**.
    
7. In **Telefonia** eseguire le operazioni seguenti:
    
   - Per disabilitare le chiamate audio e le videochiamate per l'utente, fare clic su **Audio/video disabilitati**.
    
   - Per abilitare le comunicazioni audio da PC a PC per l'utente, ma non il controllo delle chiamate remote o VoIP aziendale, fare clic su **Solo da PC a PC**. Specificare un valore per **URI linea** per il telefono utilizzato dall'utente per le comunicazioni audio da PC a PC.
    
   - Per instradare le chiamate telefoniche dell'utente utilizzando l'infrastruttura di Skype for business in base alla classe dei criteri di servizio, inclusa la comunicazione audio da PC a PC, fare clic su **VoIP aziendale**. In **URI linea** specificare il numero di telefono per VoIP aziendale. In **Criteri dial plan** e **Criteri vocali** specificare i criteri appropriati per l'utente. Per specificare le regole di normalizzazione per la conversione dei numeri di telefono composti dall'utente nel formato E.164, selezionare il profilo località appropriato in **Criteri percorso**.
    
   - Per abilitare il controllo delle chiamate remote, che consente agli utenti di controllare la linea telefonica desktop da Skype for Business Server per effettuare chiamate da PC a PC e da PC a telefono, fare clic su **Remote Call Control**. In **URI linea** specificare il numero di telefono per il controllo delle chiamate remote. L'utente deve disporre di un telefono da scrivania e di una connessione PBX per il routing delle chiamate.
    
## <a name="move-users-to-another-pool"></a>Spostare gli utenti in un altro pool
<a name="Move_Users"> </a>

È possibile utilizzare il pannello di controllo di Skype for Business Server per assegnare gli utenti a un server o un pool specifico.
  
> [!TIP]
> Lo spostamento di tutti gli utenti esistenti da un pool di origine che esegue Lync Server 2010 o versioni precedenti a un pool di destinazione di Skype for Business Server in un ambiente di Active Directory complesso potrebbe provocare una replica di Active Directory più lenta. Per evitare questo, è possibile utilizzare i filtri di ricerca per spostare gli utenti da pool che eseguono Lync Server 2010 o versioni precedenti separatamente oppure è possibile utilizzare Skype for Business Server Management Shell per spostare gli utenti con i cmdlet. Inoltre, la funzionalità del filtro è compatibile con gli utenti di Skype for Business Server. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Per spostare un gruppo selezionato di utenti in un server o un pool diverso

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **Utenti**.
    
4. Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, nome, cognome, nome dell'account Gestione account di protezione, indirizzo SIP o URI (Uniform Resource Identifier (URI) di linea dell'account utente desiderato e quindi fare clic su **Trova**. 
    
5. Nell'elenco della tabella selezionare uno o più utenti specifici. 
    
6. Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.
    
7. In **Sposta utenti** selezionare il pool in cui spostare gli utenti in **Pool di registrazione di destinazione**.
    
8. (Facoltativo) Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **Forza**.
    
    > [!CAUTION]
    > Se si seleziona **Forza**, l'account utente viene spostato, ma i dati utente associati vengono eliminati, ad esempio le conferenze pianificate dall'utente. Se non si seleziona questa casella di controllo, vengono spostati sia l'account sia i dati associati. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Per spostare tutti gli utenti da un server o un pool a un server o un pool diverso

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **Utenti**.
    
4. Scegliere **Sposta tutti gli utenti nel pool** dal menu **Azione**.
    
5. In **Sposta utenti** selezionare il pool contenente gli account utente da spostare in **Pool di registrazione di origine**.
    
6. In **Pool di registrazione di destinazione** selezionare il pool in cui spostare gli utenti.
    
7. (Facoltativo) Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **Forza**.
    
    > [!CAUTION]
    > Se si seleziona **Forza**, l'account utente viene spostato, ma i dati utente associati vengono eliminati, ad esempio le conferenze pianificate dall'utente. Se non si seleziona questa casella di controllo, vengono spostati sia l'account sia i dati associati. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Per spostare gli utenti da un pool a un altro mediante un filtro

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **Utenti**.
    
4. In **ricerca utente** fare clic su **Cerca** e quindi su **Aggiungi filtro**.
    
5. Nei criteri di ricerca selezionare **Pool di registrazione**, **Uguale a**, **FQDN pool** e quindi fare clic su **Trova**.
    
6. Scegliere **Sposta tutti gli utenti nel pool** dal menu **Azione**.
    
    > [!NOTE]
    > Quando a un set esistente di utenti viene applicato un filtro, l'opzione **Sposta tutti gli utenti nel pool** si trova nel contesto di un subset filtrato di utenti, non di **tutti** i possibili utenti.
  
7. In **Sposta utenti** selezionare il pool contenente gli account utente da spostare in **Pool di registrazione di origine**.
    
8. In **Pool di registrazione di destinazione** selezionare il pool in cui spostare gli utenti.
    
9. (Facoltativo) Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **Forza**.
    
    > [!CAUTION]
    > Se si seleziona **Forza**, l'account utente viene spostato, ma i dati utente associati vengono eliminati, ad esempio le conferenze pianificate dall'utente e i contatti. Se non si seleziona questa casella di controllo, vengono spostati sia l'account sia i dati associati. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Per spostare gli utenti da un pool a un altro utilizzando i cmdlet di Windows PowerShell

1. A seconda del modo in cui vengono eseguiti i comandi di Windows PowerShell, ovvero localmente o in remoto, è necessario eseguire l'accesso come membri dei ruoli amministrativi corretti di Skype for Business Server, come indicato di seguito:
    
   a. Se si eseguono i comandi nel computer locale, ad esempio si accede direttamente a un front end server, eseguire l'accesso al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **delegate Setup Permissions**.
    
   b. Se si eseguono i comandi in remoto in un altro computer (ad esempio, si accede al computer e si eseguono i comandi in remoto in un front end server Standard Edition): da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business** e quindi su **Skype for Business Server Management Shell**.
    
3. Per spostare singoli utenti, utilizzare il cmdlet Move-CsUser come indicato di seguito:
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    Dove l'utente da spostare si chiama Luisa Cazzaniga e verrà spostato dal pool principale assegnato al pool pool01.contoso.net
    
4. Per spostare un numero elevato di utenti, utilizzare i filtri con il cmdlet **Get-CsUser** e passare il set di utenti risultanti a **Move-CsUser**:
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    I comandi **Get-CsUser** e **Move-CsUser** combinati potrebbero risultare come segue:
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


