---
title: Verificare la topologia in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
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
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: "Riepilogo: informazioni su come verificare che la topologia di Skype for Business Server e i server Active Directory funzionino come previsto. Scaricare una versione di valutazione gratuita di Skype for Business Server da Microsoft Evaluation Center all'indirizzo: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ."
ms.openlocfilehash: 0c2307f3ad0416a7175d92a1440744dbda9b31d3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833836"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Verificare la topologia in Skype for Business Server
 
**Riepilogo:** Informazioni su come verificare che la topologia di Skype for Business Server e i server Active Directory funzionino come previsto. Scaricare una versione di valutazione gratuita di Skype for Business Server da [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Dopo aver pubblicato la topologia e i componenti di sistema di Skype for Business Server installati in ognuno dei server della topologia, è possibile verificare che la topologia funzioni come previsto. Ciò include la verifica che la configurazione si è propagata a tutti i server di Active Directory in modo che l'intero dominio conosca Skype for business sia disponibile nel dominio. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come indicato nel diagramma. La verifica della topologia è il passaggio 8 di 8.
  
![Diagramma panoramica.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Testare la distribuzione del pool Front End

Il passaggio finale consiste nel testare il pool Front end e verificare che i client Skype for business possano comunicare tra loro. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Aggiungere utenti e verificare la connettività del client

1. Utilizzare computer e utenti di Active Directory per aggiungere l'oggetto utente di Active Directory del ruolo di amministratore per la distribuzione di Skype for Business Server (in cui è installato il pannello di controllo di Skype for Business Server) nel gruppo **CsAdministrator** .
    
    > [!IMPORTANT]
    > Se non si aggiungono gli utenti e i gruppi corretti al gruppo CSAdministrator, verrà visualizzato un messaggio di errore quando si apre il pannello di controllo di Skype for Business Server che legge "non autorizzato: accesso negato a causa di un errore di autorizzazione del controllo di accesso basato sui ruoli (RBAC)". 
  
2. Se l'oggetto utente è connesso, disconnettersi e rieseguire l'accesso per registrare la nuova assegnazione al gruppo.
    
    > [!NOTE]
    > L'account utente non può essere l'amministratore locale di qualsiasi server che esegue Skype for Business Server. 
  
3. Utilizzare l'account amministrativo per accedere al computer in cui è installato il pannello di controllo di Skype for Business Server.
    
4. Avviare il pannello di controllo di Skype for Business Server e quindi specificare le credenziali, se richiesto. Il pannello di controllo di Skype for Business Server Visualizza le informazioni sulla distribuzione.
    
5. Sulla barra di spostamento sinistra fare clic su **topologia** e quindi verificare che lo stato del servizio visualizzi un computer con una freccia verde e che un segno di spunta verde per lo stato di replica sia accanto a ciascun ruolo di Skype for Business Server distribuito e portato online. 
    
6. Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi su **Abilita utenti**. 
    
7. Nella pagina **nuovo utente di Skype for Business Server** fare clic su **Aggiungi**.
    
8. Per definire i parametri di ricerca per gli oggetti che si desidera trovare, nella pagina **Seleziona da Active Directory** è possibile selezionare **Cerca** e quindi facoltativamente fare clic su **Aggiungi filtro**. È anche possibile selezionare **Ricerca LDAP** e immettere un'espressione LDAP per filtrare o limitare gli oggetti che verranno restituiti. Dopo aver scelto le opzioni di ricerca, fare clic su **trova**.
    
9. Nel riquadro dei risultati della ricerca, selezionare gli utenti che si desidera aggiungere, quindi fare clic su **OK**.
    
10. Nella pagina **nuovo utente di Skype for Business Server** , gli utenti selezionati sono presenti nella visualizzazione **utenti** . Nell'elenco **Assegna utenti a un pool** selezionare il server in cui devono risiedere gli utenti.
    
    Di seguito è riportato un elenco delle opzioni che è possibile utilizzare per configurare gli oggetti.
    
    - **Generare l'URI SIP dell'utente**
    
    - **Telefonia**
    
    - **URI linea**
    
    - **Criteri conferenza**
    
    - **Criteri versione client**
    
    - **Criteri PIN**
    
    - **Criteri di accesso esterno**
    
    - **Criteri di archiviazione**
    
    - **Criteri percorso**
    
    - **Criteri client**
    
    Per testare la funzionalità di base, selezionare l'opzione desiderata per l'impostazione **URI SIP dell'utente** (le altre opzioni nella configurazione utilizzano le impostazioni predefinite) e quindi fare clic su **Abilita**, come mostrato nella figura.
    
     ![Abilitare gli utenti nel pannello di controllo.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Viene visualizzata una pagina di riepilogo in cui viene visualizzato un segno di spunta nella colonna **Enabled** per indicare che gli utenti sono impostati. La colonna **Indirizzo SIP** visualizza l'indirizzo necessario per la configurazione dell'accesso degli utenti.
    
     ![Utenti aggiunti al pannello di controllo di Skype for Business Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Registrare un utente in un computer aggiunto al dominio e a un altro utente su un altro computer nel dominio.
    
13. Installare il client Skype for business in ognuno dei due computer client e quindi verificare che entrambi gli utenti siano in grado di accedere a Skype for Business Server e possano inviare messaggi istantanei.
    

