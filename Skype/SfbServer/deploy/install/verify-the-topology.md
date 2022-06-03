---
title: Verificare la topologia in Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Riepilogo: informazioni su come verificare che la topologia Skype for Business Server e i server Active Directory funzionino come previsto.'
ms.openlocfilehash: ec63977f4c70845f39aafe3521591ec93777f7d5
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860547"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Verificare la topologia in Skype for Business Server
 
**Riepilogo:** Informazioni su come verificare che la topologia Skype for Business Server e i server Active Directory funzionino come previsto.
  
Dopo aver pubblicato la topologia e aver installato i componenti di sistema Skype for Business Server in ognuno dei server della topologia, è possibile verificare che la topologia funzioni come previsto. Ciò include la verifica che la configurazione sia stata propagata a tutti i server Active Directory in modo che l'intero dominio sappia che Skype for Business è disponibile nel dominio. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come descritto nel diagramma. La verifica della topologia è il passaggio 8 dell'8.
  
![Diagramma di panoramica.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Testare la distribuzione del pool Front End

Il passaggio finale consiste nel testare il pool Front End e verificare che Skype for Business client possano comunicare tra loro. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Aggiungere utenti e verificare la connettività client

1. Usare Computer e utenti di Active Directory per aggiungere l'oggetto utente di Active Directory del ruolo di amministratore per la distribuzione Skype for Business Server (in cui è installato Skype for Business Server Pannello di controllo) al gruppo **CSAdministrator**.
    
    > [!IMPORTANT]
    > Se non si aggiungono gli utenti e i gruppi appropriati al gruppo CsAdministors, si riceverà un errore quando si apre Skype for Business Server Pannello di controllo che indica che l'accesso non autorizzato è negato a causa di un errore di autorizzazione del controllo degli accessi in base al ruolo. 
  
2. Se l'oggetto utente è connesso, disconnettersi e rieseguire l'accesso per registrare la nuova assegnazione al gruppo.
    
    > [!NOTE]
    > L'account utente non può essere l'amministratore locale di qualsiasi server che esegue Skype for Business Server. 
  
3. Usare l'account amministrativo per accedere al computer in cui è installato Skype for Business Server Pannello di controllo.
    
4. Avviare Skype for Business Server Pannello di controllo e quindi specificare le credenziali, se richiesto. Skype for Business Server Pannello di controllo visualizza le informazioni sulla distribuzione.
    
5. Nella barra di spostamento a sinistra fare clic su **Topologia**, quindi verificare che lo stato del servizio mostri un computer con una freccia verde e che accanto a ogni ruolo di Skype for Business Server distribuito e portato online sia presente un segno di spunta verde per lo stato della replica. 
    
6. Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi su **Abilita utenti**. 
    
7. Nella pagina **Nuovo utente Skype for Business Server** fare clic su **Aggiungi**.
    
8. Per definire i parametri di ricerca per gli oggetti che si desidera trovare, nella pagina **Seleziona da Active Directory** è possibile selezionare **Cerca** e quindi facoltativamente fare clic su **Aggiungi filtro**. È anche possibile selezionare **Ricerca LDAP** e immettere un'espressione LDAP per filtrare o limitare gli oggetti che verranno restituiti. Dopo aver deciso le opzioni di ricerca, fare clic su **Trova**.
    
9. Nel riquadro Risultati della ricerca selezionare gli utenti da aggiungere e quindi fare clic su **OK**.
    
10. Nella pagina **Nuovo utente Skype for Business Server** gli utenti selezionati si trovano nella visualizzazione **Utenti**. Nell'elenco **Assegna utenti a un pool** selezionare il server in cui devono risiedere gli utenti.
    
    Di seguito è riportato un elenco di opzioni che è possibile usare per configurare gli oggetti.
    
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
    
    Per testare la funzionalità di base, selezionare l'opzione preferita per l'impostazione **GENERA URI SIP dell'utente** (le altre opzioni della configurazione usano le impostazioni predefinite) e quindi fare clic su **Abilita**, come illustrato nella figura.
    
     ![Abilitare gli utenti in Pannello di controllo.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Viene visualizzata una pagina di riepilogo che mostra un segno di spunta nella colonna **Abilitato** per indicare che gli utenti sono configurati. La colonna **Indirizzo SIP** visualizza l'indirizzo necessario per la configurazione dell'accesso degli utenti.
    
     ![Utenti aggiunti a Skype for Business Server Pannello di controllo.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Accedere un utente a un computer aggiunto al dominio e un altro utente a un altro computer nel dominio.
    
13. Installare Skype for Business client in ognuno dei due computer client e quindi verificare che entrambi gli utenti possano accedere a Skype for Business Server e inviare messaggi istantanei l'uno all'altro.
    

