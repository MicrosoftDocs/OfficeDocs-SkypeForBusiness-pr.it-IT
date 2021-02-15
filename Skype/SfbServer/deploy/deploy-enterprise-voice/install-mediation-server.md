---
title: Installare i file per Mediation Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Riepilogo: informazioni su come installare i file per Mediation Server in Skype for Business Server.'
ms.openlocfilehash: 80f25d9fab37555d5b4e9dc3d610c5c9037c934d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830796"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Installare i file per Mediation Server in Skype for Business Server
 
**Riepilogo:** Informazioni su come installare i file per Mediation Server in Skype for Business Server.
  
Per eseguire questa procedura, è necessario accedere al server almeno come amministratore locale e come utente di dominio appartenente almeno al gruppo RTCUniversalReadOnlyAdmin.
  
Seguire i passaggi descritti in questo argomento per eseguire la Distribuzione guidata di Skype for Business Server per installare i file per Mediation Server in un computer aggiunto a un pool Mediation Server dopo aver utilizzato Generatore di topologie per definire e pubblicare il pool. Quando si installano file mediation server, è inoltre necessario installare e assegnare il certificato richiesto da ogni computer in un pool Mediation Server. 
  
> [!NOTE]
> In questo argomento si presuppone che nella topologia sia già stato definito e pubblicato un pool Mediation Server autonomo, come descritto in Distribuire un Mediation Server in Generatore di topologie [in Skype for Business Server.](deploy-a-mediation-server.md) 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Per installare i file per un pool Mediation Server autonomo

1. Dal supporto di installazione fare clic con il pulsante destro del\Setup\amd64\Setup.exee quindi scegliere _\<installation media\>_ **** Esegui **come amministratore.**
    
2. Nella pagina **Percorso di installazione** fare clic su **OK**.
    
3. Nella pagina **Contratto di licenza con l'utente finale** fare clic su **Accetto** e quindi su **OK**. Questa operazione è obbligatoria per proseguire.
    
4. Nella pagina **Distribuzione guidata di Skype for Business Server** fare clic su Installa o aggiorna il sistema Skype for Business **Server.**
    
5. Accanto a **Passaggio 1: Installazione dell'archivio di configurazione locale** fare clic su **Esegui** e quindi seguire le istruzioni visualizzate sullo schermo.
    
6. Nella pagina **Configura la replica locale dell'archivio di gestione centrale** accettare l'impostazione predefinita **Recupera direttamente dall'archivio di gestione centrale** e quindi fare clic su **Avanti**.
    
7. Nella pagina **Esecuzione comandi in corso**, quando lo stato dell'attività risulta completato,fare clic su **Fine**.
    
8. Accanto al **passaggio 2: Installazione o rimozione dei componenti di Skype for Business Server,** fare clic su **Esegui** e quindi su **Avanti.**
    
9. Nella pagina **Esecuzione comandi in corso**, quando lo stato dell'attività risulta completato,fare clic su **Fine**.
    
10. Accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati** fare clic su **Esegui**. Seguire le istruzioni visualizzate sullo schermo, accettando le impostazioni predefinite. Il Mediation Server richiede un certificato, quindi il **Passaggio 3** verrà eseguito due volte, una per emettere il certificato necessario e l'altra per assegnarlo.
    
11. Dopo che il certificato è stato emesso e assegnato correttamente, accanto **Passaggio 4: Avvia servizi** fare clic su **Esegui** e quindi seguire le istruzioni visualizzate sullo schermo.
    
12. Al termine del **Passaggio 4**, riavviare il server e accedere come membro del gruppo DomainAdmins.
    
13. Nel computer in cui si esegue il Pannello di  controllo di Skype for Business Server, verificare nella pagina Topologia del Pannello di controllo di Skype for Business Server che lo stato del servizio del Mediation Server sia visualizzato come un segno di spunta verde. Se invece appare una X rossa, selezionare il Mediation Server. Scegliere **Avvia tutti i servizi** dal menu **Azione**. 
    
Se sono stati aggiunti più computer al pool Mediation Server, eseguire i passaggi di questa procedura in tutti gli altri computer del pool Mediation Server. Se non è necessario installare file per Mediation Server per altri computer, seguire le procedure [descritte in](configure-trunks.md) Configurare i trunk in Skype for Business Server per configurare le impostazioni per la connessione trunk tra il pool Mediation Server (o tutti i Mediation Server in un sito) e il relativo peer.

