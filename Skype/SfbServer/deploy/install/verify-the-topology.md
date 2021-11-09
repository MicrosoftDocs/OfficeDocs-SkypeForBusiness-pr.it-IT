---
title: Verificare la topologia in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
description: "Riepilogo: informazioni su come verificare che la topologia Skype for Business Server e i server Active Directory funzionino come previsto. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Centro di valutazione Microsoft all'indirizzo: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ."
ms.openlocfilehash: 32d9e4302109ef9a7d5cb34946722eb8a8e9f38c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864263"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Verificare la topologia in Skype for Business Server
 
**Riepilogo:** Informazioni su come verificare che la Skype for Business Server e i server Active Directory funzionino come previsto. Scarica una versione di valutazione gratuita di Skype for Business Server dal [Centro di valutazione Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
Dopo aver pubblicato la topologia e aver installato i componenti di sistema di Skype for Business Server in ognuno dei server della topologia, è possibile verificare che la topologia funzioni come previsto. Ciò include la verifica che la configurazione sia stata propagata a tutti i server Active Directory in modo che l'intero Skype for Business sia disponibile nel dominio. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. È tuttavia necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come illustrato nel diagramma. Verificare che la topologia sia il passaggio 8 di 8.
  
![Diagramma di panoramica.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Testare la distribuzione del pool Front End

Il passaggio finale consiste nel testare il pool Front End e verificare che Skype for Business client possano comunicare tra loro. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Aggiungere utenti e verificare la connettività client

1. Utilizzare Utenti e computer di Active Directory per aggiungere l'oggetto utente di Active Directory del ruolo di amministratore per la distribuzione di Skype for Business Server (in cui è installato il Pannello di controllo di Skype for Business Server) al gruppo **CSAdministrator.**
    
    > [!IMPORTANT]
    > Se non si aggiungono gli utenti e i gruppi appropriati al gruppo CsAdministors, all'apertura del Pannello di controllo di Skype for Business Server verrà visualizzato un messaggio di errore che indica "Accesso non autorizzato: accesso negato a causa di un errore di autorizzazione RBAC (Role-Based Access Control) ". 
  
2. Se l'oggetto utente è connesso, disconnettersi e rieseguire l'accesso per registrare la nuova assegnazione al gruppo.
    
    > [!NOTE]
    > L'account utente non può essere l'amministratore locale di alcun server che esegue Skype for Business Server. 
  
3. Utilizzare l'account amministrativo per accedere al computer in cui Skype for Business Server è installato il Pannello di controllo.
    
4. Avviare Skype for Business Server Pannello di controllo e quindi fornire le credenziali, se richiesto. Skype for Business Server Nel Pannello di controllo vengono visualizzate informazioni sulla distribuzione.
    
5. Sulla barra di spostamento sinistra fare clic su Topologia e quindi verificare che lo stato del servizio mostra un computer con una freccia verde e che accanto a ogni ruolo di Skype for Business Server distribuito e portato online sia presente un segno di spunta verde. 
    
6. Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi su **Abilita utenti**. 
    
7. Nella pagina **Nuovo Skype for Business Server utente** fare clic su **Aggiungi.**
    
8. Per definire i parametri di ricerca per gli oggetti che si desidera trovare, nella pagina **Seleziona da Active Directory** è possibile selezionare **Cerca** e quindi facoltativamente fare clic su **Aggiungi filtro**. È anche possibile selezionare **Ricerca LDAP** e immettere un'espressione LDAP per filtrare o limitare gli oggetti che verranno restituiti. Dopo aver deciso le opzioni di ricerca, fare clic su **Trova.**
    
9. Nel riquadro Risultati ricerca selezionare gli utenti che si desidera aggiungere e quindi fare clic su **OK.**
    
10. Nella pagina **Nuovo Skype for Business Server utente** gli utenti selezionati sono visualizzati nella **visualizzazione** Utenti. **Nell'elenco Assegna utenti a un pool** selezionare il server in cui devono risiedere gli utenti.
    
    Di seguito è riportato un elenco di opzioni che è possibile utilizzare per configurare gli oggetti.
    
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
    
    Per testare la funzionalità di base, selezionare l'opzione desiderata per **l'impostazione Genera URI SIP dell'utente** (le altre opzioni nella configurazione usano le impostazioni predefinite), quindi fare clic su **Abilita**, come illustrato nella figura.
    
     ![Abilitare gli utenti nel Pannello di controllo.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Viene visualizzata una pagina di riepilogo che mostra un segno di spunta nella **colonna Abilitato** per indicare che gli utenti sono stati programmati. La colonna **Indirizzo SIP** visualizza l'indirizzo necessario per la configurazione dell'accesso degli utenti.
    
     ![Utenti aggiunti al Skype for Business Server Pannello di controllo.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Accedere a un computer aggiunto al dominio e a un altro utente a un altro computer del dominio.
    
13. Installare Skype for Business client in ognuno dei due computer client e quindi verificare che entrambi gli utenti possano accedere a Skype for Business Server e inviare messaggi istantanei l'uno all'altro.
    

