---
title: Creare la progettazione della topologia iniziale per Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: Dopo aver completato l'installazione dello strumento di pianificazione di Skype for Business Server, è possibile avviare lo strumento di pianificazione e iniziare a progettare l'infrastruttura di Skype for Business Server 2015 proposta.
ms.openlocfilehash: 7de930de8d7e194f14145c1a976fbe6b96cf234a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834966"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Creare la progettazione della topologia iniziale per Skype for Business Server 2015

Dopo aver completato l'installazione dello strumento di pianificazione di Skype for Business Server, è possibile avviare lo strumento di pianificazione e iniziare a progettare l'infrastruttura di Skype for Business Server 2015 proposta.

> [!NOTE]
>  Lo strumento di pianificazione è uno strumento basato su procedure guidate con guide dettagliate per informare il processo decisionale nella progettazione dei siti e della topologia. Questo argomento non è una guida esaustiva, ma è sufficiente per iniziare a utilizzare lo strumento di pianificazione nelle sessioni di progettazione.

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Per iniziare a utilizzare lo strumento di pianificazione e creare un progetto iniziale

1. Avviare lo strumento di pianificazione di Skype for Business Server 2015: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015** e quindi fare clic su **strumento di pianificazione**.

2. Dopo che lo strumento di pianificazione è stato avviato, viene visualizzata la pagina **Benvenuto allo strumento di pianificazione per Skype for Business Server 2015** . Per iniziare la progettazione, scegliere una delle opzioni seguenti:

   - **Opzione 1: introduzione** Facendo clic su **Introduzione** viene fornita una serie di domande di intervista specifiche per definire i criteri. Dopo aver completato la sezione iniziale del questionario di **Per iniziare**, passare alla sezione **Progetta siti** per definire l'architettura dei siti. Per completare questa opzione, procedere al passaggio 3.

   - **Opzione 2: progettare i siti** Se **si fa** clic su **siti di progettazione** nella pagina di benvenuto, vengono ignorate le domande relative alle interviste presentate nella sezione Introduzione. Le informazioni che sarebbero state raccolte rispondendo alle domande di intervista nella sezione **Introduzione** sono impostate su valori predefiniti con questa opzione. Facendo clic su **siti di progettazione**, il progettista esperto può ignorare l'intervista iniziale e modificare i valori predefiniti, in base alle esigenze, nella pagina iniziale dei **siti centrali** . Per completare questa opzione, ignorare i passaggi da 3 a 5 e iniziare dal passaggio 6.

   - **Opzione 3: visualizzare la topologia salvata** Se è stata già completata e salvata una topologia mediante l'utilizzo precedente dello strumento di pianificazione, è possibile ignorare la maggior parte di questi passaggi e iniziare aprendo e visualizzando la topologia. È inoltre possibile apportare modifiche e aggiornamenti alla topologia, salvarla nuovamente e quindi esportarla in Microsoft Excel o Microsoft Visio. Per completare questa opzione, ignorare i passaggi da 3 a 12 e iniziare dal passaggio 13.

3. Fare **clic su** inizia per iniziare a progettare la topologia di Skype for Business Server 2015.

4. Rispondere alle domande di ogni sezione selezionando i criteri appropriati per il progetto e quindi fare clic su **Avanti** per passare alla pagina successiva della procedura guidata. Fare clic su **indietro** per apportare modifiche alle pagine precedenti.

    > [!TIP]
    > Ogni pagina contiene una descrizione dei criteri di selezione e alcuni consigli in base alle procedure preferite e alla pianificazione della capacità. Se si desiderano ulteriori dettagli, **fare clic su ulteriori informazioni** per leggere i dati dettagliati dalla documentazione relativa alla pianificazione di Skype for Business Server 2015 nel sito Web Microsoft. È necessario disporre della connettività Internet per accedere al sito Web Microsoft.

5. Selezionare le opzioni appropriate per la progettazione. Dopo la definizione dei criteri iniziali, verrà visualizzata la conferma del completamento della panoramica iniziale.

6. Fare clic su **progetta siti** per definire il sito centrale.

    > [!NOTE]
    > Ogni topologia di Skype for Business Server 2015 avrà almeno un sito centrale. La struttura può disporre di un unico sito centrale, un sito centrale con un numero di siti di succursale, un numero di siti centrali o un numero di siti centrali con siti di succursale associati a ogni sito centrale.

7. In **nome sito** Digitare il nome che identificherà questo sito centrale.

8. Negli **utenti di Site homed** Digitare il numero previsto di utenti simultanei locali che verranno ospitati in questo sito centrale.

9. Negli **utenti cloud homed** Digitare il numero previsto di utenti simultanei online che verranno ospitati in questo sito centrale.

10. Modificare le selezioni per la collaborazione online, gli utenti, la voce, le opzioni di distribuzione aggiuntive o le applicazioni server, in base alle esigenze.

    > [!IMPORTANT]
    > A questo punto della struttura è possibile selezionare o deselezionare solo le opzioni per la distribuzione. Tuttavia, è possibile configurare altre opzioni in una fase successiva dello strumento di pianificazione. Alcune opzioni non sono disponibili e non possono essere deselezionate. Inoltre, può essere necessario deselezionare un'opzione per deselezionarne un'altra. Ad esempio, se si deseleziona l'opzione VoIP **aziendale** in voce, vengono cancellate anche le opzioni del **gruppo di risposta**, **annuncio** e **parcheggio di chiamata** in applicazioni server (tutte funzionalità di VoIP aziendale).

11. Dopo aver definito il nome del sito e il numero di utenti, fare clic su **Avanti**.

12. Nelle pagine seguenti sono disponibili informazioni su domini SIP, Impostazioni conferenza, impostazioni vocali e infrastruttura, messaggistica unificata di Exchange, accesso utente esterno, impostazioni chat persistente, impostazioni client, opzioni di collocazione e siti di succursale. Rispondere a queste domande nel modo appropriato.

13. L'ultima domanda richiede se si desidera creare un altro sito centrale. Se si seleziona **Sì**, lo strumento di pianificazione torna alla pagina siti centrali. Se si seleziona **No**, fare clic su **Avanti** e quindi su **Disegna** per visualizzare la visualizzazione Topologia globale di alto livello.

14. Per visualizzare una topologia esistente, fare clic su **Visualizza**.

15. Fare clic sul file XML che corrisponde alla topologia salvata in precedenza e quindi su **Apri**.

16. Nello strumento di pianificazione viene visualizzata la pagina della topologia globale. È ora possibile avviare la modifica, l'aggiornamento o la modifica della topologia utilizzando gli strumenti disponibili nello strumento di pianificazione.

## <a name="see-also"></a>Vedere anche

[Modifica della progettazione](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
