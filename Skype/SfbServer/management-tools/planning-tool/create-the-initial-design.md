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
ms.openlocfilehash: 756c59ce0598af186a5cedabe250f7f1e7ec323c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098682"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Creare la progettazione della topologia iniziale per Skype for Business Server 2015

Dopo aver completato l'installazione dello strumento di pianificazione di Skype for Business Server, è possibile avviare lo strumento di pianificazione e iniziare a progettare l'infrastruttura di Skype for Business Server 2015 proposta.

> [!NOTE]
>  Lo strumento di pianificazione è uno strumento guidato da procedure guidate con guide dettagliate per informare il processo decisionale nella progettazione dei siti e della topologia. Questo argomento non è inteso come una guida esaustiva, ma semplicemente per iniziare a usare lo strumento di pianificazione nelle sessioni di progettazione.

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Per iniziare a utilizzare lo strumento di pianificazione e creare un progetto iniziale

1. Avviare lo strumento di pianificazione di Skype for Business Server 2015: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server 2015** e quindi Strumento **di pianificazione.**

2. Dopo l'avvio dello strumento di pianificazione, viene visualizzata la pagina Iniziale dello strumento di **pianificazione per Skype for Business Server 2015.** Scegliere una delle opzioni seguenti per iniziare la progettazione:

   - **Opzione 1: Introduzione** Facendo **clic su Introduzione** viene fornita una serie specifica di domande di colloquio con selezioni pertinenti per definire i criteri. Dopo aver completato la sezione iniziale del questionario di **Per iniziare**, passare alla sezione **Progetta siti** per definire l'architettura dei siti. Per completare questa opzione, procedere al passaggio 3.

   - **Opzione 2: Progettare siti** Se **si fa** clic su Progetta siti nella pagina di benvenuto, vengono ignorate le domande del colloquio presentate nella sezione **Introduzione.** Le informazioni che sarebbero state raccolte rispondendo alle domande del colloquio **nella** sezione Introduzione sono impostate sui valori predefiniti con questa opzione. Facendo clic **su Siti di** progettazione, il progettista esperto può ignorare il colloquio iniziale e modificare i valori predefiniti, in base alle esigenze, nella pagina iniziale **siti** centrali. Per completare questa opzione, ignorare i passaggi da 3 a 5 e iniziare dal passaggio 6.

   - **Opzione 3: visualizzare la topologia salvata** Se è già stata completata e salvata una topologia tramite l'utilizzo precedente dello strumento di pianificazione, è possibile ignorare la maggior parte di questi passaggi e iniziare aprendo e visualizzando la topologia. È inoltre possibile apportare modifiche e aggiornamenti alla topologia, salvarla di nuovo e quindi esportarla in Microsoft Excel o Microsoft Visio. Per completare questa opzione, ignorare i passaggi da 3 a 12 e iniziare dal passaggio 13.

3. Fare **clic su Introduzione** per iniziare a progettare la topologia di Skype for Business Server 2015.

4. Rispondere alle domande di ogni sezione selezionando i criteri appropriati per il progetto e quindi fare clic su **Avanti** per passare alla pagina successiva della procedura guidata. Fare **clic su** Indietro per apportare modifiche nelle pagine precedenti.

    > [!TIP]
    > Ogni pagina contiene una descrizione dei criteri di selezione e alcuni consigli in base alle procedure preferite e alla pianificazione della capacità. Se sono necessari ulteriori dettagli, fare **clic** su Ulteriori informazioni per leggere informazioni dettagliate nella documentazione relativa alla pianificazione di Skype for Business Server 2015 nel sito Web Microsoft. Per accedere al sito Web Microsoft, è necessario disporre della connettività Internet.

5. Selezionare le opzioni appropriate per la progettazione. Dopo la definizione dei criteri iniziali, verrà visualizzata la conferma del completamento della panoramica iniziale.

6. Fare **clic su Progetta siti** per definire il sito centrale.

    > [!NOTE]
    > Ogni topologia di Skype for Business Server 2015 avrà almeno un sito centrale. La progettazione può avere un singolo sito centrale, un sito centrale con un numero di siti di succursale, un numero di siti centrali o un numero di siti centrali con siti di succursale associati a ogni sito centrale.

7. In **Nome sito** digitare il nome che identificherà il sito centrale.

8. In **Utenti ospitati nel** sito digitare il numero previsto di utenti simultanei locali che verranno ospitati in questo sito centrale.

9. In **Utenti ospitati nel cloud** digitare il numero previsto di utenti simultanei online che verranno ospitati in questo sito centrale.

10. Modificare le selezioni per Collaborazione online, Utenti, Voce, Opzioni di distribuzione aggiuntive o Applicazioni server, in base alle esigenze.

    > [!IMPORTANT]
    > A questo punto della progettazione, è possibile selezionare o deselezionare solo le opzioni per la distribuzione. Tuttavia, è possibile configurare altre opzioni in una fase successiva dello strumento di pianificazione. Alcune opzioni non sono disponibili e non possono essere deselezionate. Inoltre, può essere necessario deselezionare un'opzione per deselezionarne un'altra. Ad esempio, se si deseleziona l'opzione **VoIP aziendale** in Voce,  vengono deselezionate anche le opzioni **Response Group**, **Annuncio** e Parcheggio di chiamata in Applicazioni server (tutte funzionalità di VoIP aziendale).

11. Dopo aver definito il nome del sito e il numero di utenti, fare clic su **Avanti**.

12. Nelle pagine seguenti vengono richieste informazioni sui domini SIP, sulle impostazioni delle conferenze, sulle impostazioni vocali e sull'infrastruttura, sulla messaggistica unificata di Exchange, sull'accesso degli utenti esterni, sulle impostazioni di Persistent Chat, sulle impostazioni client, sulle opzioni di collocazione e sui siti di succursale. Rispondere a queste domande nel modo appropriato.

13. La domanda finale chiede se si desidera creare un altro sito centrale. Se si seleziona **Sì,** lo Strumento di pianificazione torna alla pagina Siti centrali. Se si seleziona **No,** fare **clic su Avanti** e quindi su Disegno per visualizzare la visualizzazione topologia globale di alto livello. 

14. Per visualizzare una topologia esistente, fare clic su **Visualizza**.

15. Fare clic sul file XML che corrisponde alla topologia salvata in precedenza e quindi su **Apri**.

16. Lo Strumento di pianificazione visualizza la pagina Topologia globale. È ora possibile iniziare a modificare, aggiornare o modificare la topologia utilizzando gli strumenti disponibili nello Strumento di pianificazione.

## <a name="see-also"></a>Vedere anche

[Modifica della struttura](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)