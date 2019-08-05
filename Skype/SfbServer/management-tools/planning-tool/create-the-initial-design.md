---
title: Creare la progettazione della topologia iniziale per Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: Dopo aver completato l'installazione dello strumento di pianificazione di Skype for Business Server, si è pronti per avviare lo strumento di pianificazione e iniziare a progettare l'infrastruttura di Skype for Business Server 2015 proposta.
ms.openlocfilehash: 47a3725c1307bd6efe57fa07a955004bd6e5ff29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186749"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Creare la progettazione della topologia iniziale per Lync Server 2013

Dopo aver completato l'installazione dello strumento di pianificazione di Skype for Business Server, si è pronti per avviare lo strumento di pianificazione e iniziare a progettare l'infrastruttura di Skype for Business Server 2015 proposta.

> [!NOTE]
>  Lo strumento di pianificazione è uno strumento basato su una procedura guidata con guide dettagliate per informare il processo decisionale nella progettazione di siti e topologia. Questo argomento è inteso come guida esaustiva, ma semplicemente per iniziare a usare lo strumento pianificazione nelle sessioni di progettazione.

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Per iniziare a usare lo strumento pianificazione e creare la struttura iniziale

1. Avviare lo strumento di pianificazione di Skype for Business Server 2015: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015**e quindi fare clic su **strumento di pianificazione**.

2. Dopo l'avvio dello strumento di pianificazione, viene visualizzata la pagina **Benvenuto nello strumento di pianificazione per Skype for Business Server 2015** . Per iniziare la progettazione, scegliere una delle opzioni seguenti:

   - **Opzione 1:** iniziare Se **si fa** clic su inizia, viene fornita una serie specifica di domande di interviste con le relative selezioni per definire i criteri. Dopo aver completato la sezione iniziale **** dell'intervista introduttiva, si procede in **siti di progettazione** per definire l'architettura del sito. Per completare questa opzione, procedere con il passaggio 3.

   - **Opzione 2: progettare siti** Facendo clic su **siti di progettazione** nella pagina di benvenuto, vengono ignorate le domande relative alle interviste presentate nella sezione **Introduzione** . Le informazioni che sarebbero state raccolte rispondendo alle domande sull'intervista nella sezione **Introduzione** sono impostate su valori predefiniti con questa opzione. Facendo clic su **siti di progettazione**, il progettista esperto può ignorare l'intervista iniziale e modificare i valori predefiniti, se necessario, nella pagina iniziale dei **siti centrali** . Per completare questa opzione, saltare i passaggi 3-5 e iniziare dal passaggio 6.

   - **Opzione 3: visualizzare la topologia salvata** Se è già stata completata e salvata una topologia con l'uso precedente dello strumento di pianificazione, è possibile ignorare la maggior parte di questi passaggi e iniziare aprendo e visualizzando la topologia. È anche possibile apportare modifiche e aggiornamenti alla topologia, salvarla e quindi esportarla in Microsoft Excel o Microsoft Visio. Per completare questa opzione, saltare i passaggi 3-12 e iniziare dal passaggio 13.

3. Fare **** clic su inizia per iniziare a progettare la topologia di Skype for Business Server 2015.

4. Rispondere a ogni sezione selezionando i criteri appropriati per la struttura e quindi fare clic su **Avanti** per passare alla pagina successiva della procedura guidata. Fare clic su **indietro** per apportare modifiche alle pagine precedenti.

    > [!TIP]
    > Ogni pagina contiene una descrizione dei criteri di selezione e suggerimenti basati sulle procedure preferite e sulla pianificazione della capacità. Se sono necessari ulteriori dettagli, fare clic su **altre** informazioni per leggere i dati dettagliati della documentazione relativa alla pianificazione di Skype for Business Server 2015 nel sito Web Microsoft. Per accedere al sito Web Microsoft è necessario disporre della connettività Internet.

5. Selezionare le opzioni appropriate per la progettazione. Dopo aver definito i criteri iniziali, una pagina confermerà che la panoramica delle caratteristiche è completa.

6. Fare clic su **siti di progettazione** per definire il sito centrale.

    > [!NOTE]
    > Ogni topologia di Skype for Business Server 2015 avrà almeno un sito centrale. La progettazione può avere un singolo sito centrale, un sito centrale con numerosi siti di succursale, un numero di siti centrali o un numero di siti centrali con siti di succursale associati a ogni sito centrale.

7. In **nome sito**Digitare il nome che identificherà questo sito centrale.

8. Negli **utenti**ospitati nel sito digitare il numero previsto di utenti simultanei locali che verranno assegnati in questo sito centrale.

9. Negli **utenti cloud homed**Digitare il numero previsto di utenti concorrenti online che verranno assegnati in questo sito centrale.

10. Modificare le selezioni per la collaborazione online, gli utenti, la voce, le opzioni di distribuzione aggiuntive o le applicazioni server, se necessario.

    > [!IMPORTANT]
    > A questo punto della struttura, è possibile selezionare o deselezionare solo le opzioni per la distribuzione. È tuttavia possibile configurare altre opzioni in una fase successiva dello strumento di pianificazione. Esistono anche opzioni che non sono disponibili e non possono essere deselezionate. Inoltre, potrebbe essere necessario cancellare un'opzione per cancellarne un'altra. Se, ad esempio, si deseleziona l'opzione VoIP **aziendale** in Voice, vengono deselezionate anche le opzioni **gruppo risposta**, **annuncio**e **parcheggio di chiamata** in applicazioni server (tutte caratteristiche di Enterprise Voice).

11. Dopo aver definito un nome di sito e un numero di utenti, fare clic su **Avanti**.

12. Le pagine seguenti chiedono informazioni sui domini SIP, le impostazioni conferenza, le impostazioni vocali e l'infrastruttura, la messaggistica unificata di Exchange, l'accesso degli utenti esterni, le impostazioni della chat persistente, le impostazioni client, le opzioni di collocazione e i siti di filiale Rispondere a queste domande in base alle esigenze.

13. La domanda finale chiede se si vuole creare un altro sito centrale. Se si seleziona **Sì**, lo strumento di pianificazione torna alla pagina siti centrali. Se si seleziona **No**, fare clic su **Avanti**e quindi su **disegno** per visualizzare la visualizzazione Topologia globale di alto livello.

14. Per visualizzare una topologia esistente, fare clic su **Visualizza**.

15. Fare clic sul file XML che rappresenta la topologia salvata in precedenza e quindi fare clic su **Apri**.

16. Lo strumento di pianificazione Visualizza la pagina della topologia globale. Ora è possibile iniziare a modificare, aggiornare o modificare la topologia usando gli strumenti disponibili nello strumento di pianificazione.

## <a name="see-also"></a>Vedere anche

[Modifica della struttura](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
