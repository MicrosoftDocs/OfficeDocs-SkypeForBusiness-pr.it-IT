---
title: Installare i file per Mediation Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Riepilogo: informazioni su come installare i file per Mediation Server in Skype for Business Server.'
ms.openlocfilehash: b73832586ba4a09cc51f67bddcaf30c2f85fcca1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240530"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Installare i file per Mediation Server in Skype for Business Server
 
**Riepilogo:** Informazioni su come installare i file per Mediation Server in Skype for Business Server.
  
Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server, almeno come amministratore locale e un utente di dominio con appartenenza almeno al gruppo RTCUniversalReadOnlyAdmins.
  
Usare la procedura descritta in questo argomento per eseguire la distribuzione guidata di Skype for Business Server per installare i file per Mediation Server in un computer aggiunto a un pool di Mediation Server dopo avere usato generatore di topologie per definire e pubblicare il pool. Durante l'installazione di file Mediation Server è anche possibile installare e assegnare il certificato richiesto da ogni computer in un pool di Mediation Server. 
  
> [!NOTE]
> Questo argomento presuppone che sia già stato definito e pubblicato un pool di Mediation Server autonomo nella topologia, come descritto in [distribuire un Mediation Server in Generatore di topologie in Skype for Business Server](deploy-a-mediation-server.md). 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Per installare i file per un pool di Mediation Server autonomo

1. Dal supporto di installazione fare clic con il pulsante destro del mouse su _ \<supporto\> _ per l'installazione **\setup\amd64\Setup.exe**e quindi scegliere **Esegui come amministratore**.
    
2. Nella pagina **posizione di installazione** fare clic su **OK**.
    
3. Nella pagina **contratto di licenza con l'utente finale** fare clic su **Accetto**e quindi fare clic su **OK**. (Obbligatorio per continuare).
    
4. Nella pagina della **distribuzione guidata di Skype for Business Server** fare clic su **Installa o Aggiorna sistema di Skype for Business Server**.
    
5. Accanto al **passaggio 1: installare l'archivio configurazione locale**, fare clic su **Esegui**e quindi seguire le istruzioni visualizzate.
    
6. Nella pagina **Configura replica locale della pagina Central Management store** accettare il recupero predefinito **direttamente dall'Central Management store**e quindi fare clic su **Avanti**.
    
7. Nella pagina **esecuzione dei comandi** , quando lo stato dell'attività viene visualizzato come **completato**, fare clic su **fine**.
    
8. Accanto al **passaggio 2: configurare o rimuovere i componenti di Skype for Business Server**, fare clic su **Esegui**e quindi su **Avanti**.
    
9. Nella pagina **esecuzione dei comandi** , quando lo stato dell'attività viene visualizzato come **completato**, fare clic su **fine**.
    
10. Accanto al **passaggio 3: richiedere, installare o assegnare certificati**, fare clic su **Esegui**. Seguire le istruzioni visualizzate per accettare le impostazioni predefinite. Il Mediation Server richiede un certificato e quindi verrà eseguito due volte il **passaggio 3** : una volta per emettere il certificato richiesto e ancora una volta per assegnarlo.
    
11. Quando il certificato è stato emesso e assegnato correttamente, accanto al **passaggio 4: avviare i servizi**, fare clic su **Esegui**e quindi seguire le istruzioni visualizzate.
    
12. Quando il **passaggio 4** è stato completato correttamente, riavviare il server e accedere al server come membro del gruppo DomainAdmins.
    
13. Nel computer in cui è installato il pannello di controllo di Skype for Business Server verificare nella **** pagina topologia del pannello di controllo di Skype for Business Server che lo stato del servizio di Mediation Server sia visualizzato come segno di spunta verde. Se invece viene visualizzata una X rossa, selezionare il Mediation Server. Nel menu **azione** fare clic su **Avvia tutti i servizi**. 
    
Se sono stati aggiunti più computer al pool di Mediation Server, eseguire i passaggi descritti in questa procedura in tutti gli altri computer del pool di Mediation Server. Se non è necessario installare file per Mediation Server per altri computer, seguire le procedure descritte in [configurare Trunks in Skype for Business Server](configure-trunks.md) per configurare le impostazioni per la connessione trunk tra questo pool di Mediation Server (o tutta la mediazione Server in un sito) e il relativo peer.

