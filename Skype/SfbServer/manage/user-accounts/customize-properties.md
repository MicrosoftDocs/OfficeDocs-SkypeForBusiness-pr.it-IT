---
title: Personalizzare le proprietà dell'account utente per Skype for Business Server
ms.reviewer: ''
ms.author: v-mathavale
author: v-mathavale
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: È possibile utilizzare le procedure descritte in questa sezione per modificare le proprietà dei singoli account utente.
ms.openlocfilehash: f80847b57122539654541a444f427f4031ee6197
ms.sourcegitcommit: 2aae13454178dc2e2cbc8cca967cd181c5f9d044
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2021
ms.locfileid: "61314204"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Personalizzare le proprietà dell'account utente per Skype for Business Server
 
È possibile utilizzare le procedure descritte in questa sezione per modificare le proprietà dei singoli account utente.
 
Esistono due operazioni di base che possono essere eseguite a livello di singolo utente:
 
- [Configurare le opzioni di telefonia per un account utente specifico](#configure-telephony-options-for-a-specific-user-account)

- [Spostare gli utenti in un altro pool](#move-users-to-another-pool)
 
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Configurare le opzioni di telefonia per un account utente specifico

È possibile personalizzare le impostazioni di telefonia per un utente specifico, purché il singolo utente sia stato abilitato per Skype for Business Server e l'organizzazione supporti la telefonia.
 
Skype for Business Server telefonia degli utenti sono le seguenti:
 
|Opzioni telefoniche  |Descrizione  |
|---------|---------|
|**Audio/video disabilitati**|L'utente non può effettuare chiamate con funzionalità audio e video.|
|**Solo da PC a PC** | L'utente può effettuare solo chiamate audio o videochiamate da PC a PC.|
|**VoIP aziendale** | L'utente può utilizzare l'infrastruttura Skype for Business Server per instradare tutte le chiamate in ingresso e in uscita. Può inoltre effettuare chiamate da PC a PC.|
|**Controllo delle chiamate remote**   | L'utente può Skype for Business Server per controllare il telefono desktop e può anche effettuare chiamate da PC a PC.|
 
Per informazioni dettagliate sulla configurazione della telefonia per un'organizzazione, vedere [Enable users for VoIP aziendale in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) e Deploy VoIP aziendale in [Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) nella documentazione relativa alla distribuzione.
 
### <a name="configure-telephony-options-for-specific-users-using-new-control-panel"></a>Configurare le opzioni di telefonia per utenti specifici utilizzando il nuovo Pannello di controllo 
 
1. Apri una finestra del browser e immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.
 
2. Accedere utilizzando un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator.
 
3. Nel riquadro sinistro selezionare **Utenti**.
 
4. Nella casella **Cerca** digitare tutto o la prima parte del nome visualizzato e fare clic su **Trova**.
 
5. Nella tabella fare doppio clic sull'account utente che si desidera modificare.
 
6. Nel riquadro visualizzato fare clic sull'icona a forma di matita accanto a **Criteri assegnati.**
 
7. In **Telefonia** eseguire le operazioni seguenti:
 
    1. Per disabilitare le chiamate audio e video per l'utente, selezionare **Audio/Video disabilitato** nell'elenco a discesa.
 
    2. Per abilitare le comunicazioni audio da PC a PC per l'utente, ma non per il controllo delle chiamate remote o VoIP aziendale, selezionare Solo **da PC** a PC nell'elenco a discesa. Specificare un valore per **URI linea** per il telefono utilizzato dall'utente per le comunicazioni audio da PC a PC.
 
    3. Per instradare le chiamate telefoniche dell'utente utilizzando l'infrastruttura di Skype for Business in base ai criteri di classe del servizio, inclusa la comunicazione audio da PC a PC, selezionare VoIP aziendale nell'elenco a **discesa.** In **URI linea** specificare il numero di telefono per VoIP aziendale. In **Criteri dial plan** e **Criteri vocali** specificare i criteri appropriati per l'utente. Per specificare le regole di normalizzazione per la conversione dei numeri di telefono digitati dall'utente nel formato E.164, selezionare il profilo percorso appropriato nell'elenco a discesa **Criteri** percorso.
 
    4. Per abilitare il controllo delle chiamate remote, che consente agli utenti di controllare la linea telefonica desktop da Skype for Business Server per effettuare chiamate da PC a PC e da PC a telefono, selezionare **Controllo** chiamate remote nell'elenco a discesa. In **URI linea** specificare il numero di telefono per il controllo delle chiamate remote. L'utente deve disporre di un telefono da scrivania e di una connessione PBX per il routing delle chiamate.

> [!NOTE]
> Il nuovo Pannello di controllo non è disponibile per Skype for Business Server 2015.

### <a name="configure-telephony-options-for-specific-users-using-legacy-control-panel"></a>Configurare le opzioni di telefonia per utenti specifici utilizzando il Pannello di controllo legacy
 
1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
 
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 
 
3. Nel riquadro sinistro selezionare **Utenti**.
 
4. Nella casella **Ricerca utenti** digitare interamente o parzialmente il nome visualizzato, il nome, il cognome, il nome account del sistema degli account di sicurezza (SAM), l'indirizzo SIP o l'URI (Uniform Resource Identifier) linea dell'account utente desiderato e quindi fare clic su **Trova**.
 
5. Nella tabella selezionare l'account utente che si desidera modificare.
 
6. Dal menu **Modifica**, selezionare **Modifica**.
 
7. In **Telefonia** eseguire le operazioni seguenti:
 
    1. Per disabilitare le chiamate audio e video per l'utente, selezionare **Audio/video disabilitato.**
 
    2. Per abilitare le comunicazioni audio da PC a PC per l'utente, ma non il controllo delle chiamate remote o VoIP aziendale, selezionare Solo **da PC a PC.** Specificare un valore per **URI linea** per il telefono utilizzato dall'utente per le comunicazioni audio da PC a PC.
 
    3. Per instradare le chiamate telefoniche dell'utente utilizzando l'infrastruttura Skype for Business in base ai criteri di classe del servizio, inclusa la comunicazione audio da PC a PC, **selezionare VoIP aziendale**. In **URI linea** specificare il numero di telefono per VoIP aziendale. In **Criteri dial plan** e **Criteri vocali** specificare i criteri appropriati per l'utente. Per specificare le regole di normalizzazione per la conversione dei numeri di telefono composti dall'utente nel formato E.164, selezionare il profilo località appropriato in **Criteri percorso**.
 
    4. Per abilitare il controllo delle chiamate remote, che consente agli utenti di controllare la linea telefonica desktop da Skype for Business Server per effettuare chiamate da PC a PC e da PC a telefono, selezionare Controllo chiamate **remote.** In **URI linea** specificare il numero di telefono per il controllo delle chiamate remote. L'utente deve disporre di un telefono da scrivania e di una connessione PBX per il routing delle chiamate.

## <a name="move-users-to-another-pool"></a>Spostare gli utenti in un altro pool

È possibile utilizzare Skype for Business Server pannello di controllo per assegnare utenti a un server o a un pool specifico.
 
> [!TIP]
> Lo spostamento di tutti gli utenti esistenti da un pool di origine che esegue Lync Server 2010 o versioni precedenti a un pool di destinazione di Skype for Business Server in un ambiente Active Directory complesso potrebbe rallentare la replica di Active Directory. Per evitare questo problema, è possibile utilizzare i filtri di ricerca per spostare gli utenti dai pool che eseguono Lync Server 2010 o versioni precedenti separatamente oppure è possibile utilizzare Skype for Business Server Management Shell per spostare gli utenti con i cmdlet. Inoltre, la funzionalità di filtro funziona con Skype for Business Server utenti. 
 
### <a name="move-selected-users-to-a-different-server-or-pool-using-new-control-panel"></a>Spostare gli utenti selezionati in un altro server o pool utilizzando il nuovo Pannello di controllo

1. Apri una finestra del browser e immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.
 
2. Accedere utilizzando un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator. 
 
3. Nel riquadro sinistro selezionare **Utenti**.
 
4. Nella casella **Cerca** digitare tutto o la prima parte del nome visualizzato e fare clic su **Trova**.
 
5. Nella tabella fare doppio clic per selezionare uno o più utenti specifici nell'elenco. 

6. Nel riquadro visualizzato fare clic sull'icona a forma di matita accanto a **Pool di registrazione.**
 
7. In **Sposta utenti** selezionare il pool in cui si desidera spostare gli utenti nell'elenco a discesa.
 
8. (Facoltativo) Se il server o il pool di destinazione non è disponibile, selezionare la **casella di controllo** Forza.
 
    > [!CAUTION]
    > Se si seleziona **Forza**, l'account utente viene spostato, ma i dati utente associati vengono eliminati, ad esempio le conferenze pianificate dall'utente. Se non si seleziona questa casella di controllo, vengono spostati sia l'account sia i dati associati. 

> [!NOTE]
> Il nuovo Pannello di controllo non è disponibile per Skype for Business Server 2015.

### <a name="move-selected-users-to-a-different-server-or-pool-using-legacy-control-panel"></a>Spostare gli utenti selezionati in un server o pool diverso utilizzando il Pannello di controllo legacy

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
 
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 
 
3. Nel riquadro sinistro selezionare **Utenti**.
 
4. Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, nome, cognome, nome dell'account Gestione account di protezione, indirizzo SIP o URI (Uniform Resource Identifier (URI) di linea dell'account utente desiderato e quindi fare clic su **Trova**. 
 
5. Nell'elenco della tabella selezionare uno o più utenti specifici. 
 
6. Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.
 
7. In **Sposta utenti** selezionare il pool in cui spostare gli utenti in **Pool di registrazione di destinazione**.
 
8. (Facoltativo) Se il server o il pool di destinazione non è disponibile, selezionare la **casella di controllo** Forza.
 
    > [!CAUTION]
    > Se si seleziona **Forza**, l'account utente viene spostato, ma i dati utente associati vengono eliminati, ad esempio le conferenze pianificate dall'utente. Se non si seleziona questa casella di controllo, vengono spostati sia l'account sia i dati associati. 
 
### <a name="move-users-from-one-pool-to-a-different-pool-by-using-a-filter-using-legacy-control-panel"></a>Spostare gli utenti da un pool a un altro utilizzando un filtro tramite il Pannello di controllo legacy 

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
 
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 
 
3. Nel riquadro sinistro selezionare **Utenti**.
 
4. In **Ricerca utente** selezionare **Cerca** e quindi fare clic su **Aggiungi filtro.**
 
5. Nei criteri di ricerca selezionare **Pool di registrazione**, **Uguale a**, **FQDN pool** e quindi fare clic su **Trova**.
 
6. Scegliere **Sposta** tutti gli utenti nel pool dal menu **Azione.**
 
    > [!NOTE]
    > Quando a un set esistente di utenti viene applicato un filtro, l'opzione **Sposta tutti gli utenti nel pool** si trova nel contesto di un subset filtrato di utenti, non di **tutti** i possibili utenti.
 
7. In **Sposta utenti** selezionare il pool contenente gli account utente da spostare in **Pool di registrazione di origine**.
 
8. In **Pool di registrazione di destinazione** selezionare il pool in cui spostare gli utenti.
 
9. (Facoltativo) Se il server o il pool di destinazione non è disponibile, selezionare la **casella di controllo** Forza.
 
    > [!CAUTION]
    > Se si seleziona **Forza**, l'account utente viene spostato, ma i dati utente associati vengono eliminati, ad esempio le conferenze pianificate dall'utente e i contatti. Se non si seleziona questa casella di controllo, vengono spostati sia l'account sia i dati associati. 
 
### <a name="move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Spostare gli utenti da un pool a un altro utilizzando Windows PowerShell cmdlet

1. A seconda di come si eseguono Windows PowerShell comandi, ovvero in locale o in remoto, è necessario accedere come membro dei ruoli amministrativi Skype for Business Server corretti, come indicato di seguito:
 
    1. Se si eseguono i comandi nel computer locale (ad esempio, si accede direttamente a un Front End Server): accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **Delegate Setup Permissions**.
 
    2. Se i comandi vengono eseguiti in remoto in un altro computer, ad esempio si accede al computer ed eseguire i comandi in remoto in un Front End Server di edizione Standard: da un account utente assegnato al ruolo CsUserAdministrator o csAdministrator, accedere a qualsiasi computer nella distribuzione interna.
 
2. Avviare la Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business** e quindi fare clic su Skype for Business Server **Management Shell.**
 
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


