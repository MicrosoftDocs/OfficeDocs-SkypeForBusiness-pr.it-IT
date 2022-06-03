---
title: Installare gli strumenti di amministrazione in Skype for Business Server
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
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: "Riepilogo: informazioni su come installare gli strumenti di amministrazione necessari per un'installazione di Skype for Business Server."
ms.openlocfilehash: e18ad5953eb063cdb91ea2927ad03ed1057c840a
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860527"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Installare gli strumenti di amministrazione in Skype for Business Server
 
**Riepilogo:** Informazioni su come installare gli strumenti di amministrazione necessari per un'installazione di Skype for Business Server.
  
Gli strumenti di amministrazione includono Generatore di topologie e il Pannello di controllo. Gli strumenti di amministrazione devono essere installati in almeno un server nella topologia o in una workstation di gestione a 64 bit che esegue una versione del sistema operativo Windows supportata per Skype for Business Server. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come descritto nel diagramma. L'installazione degli strumenti di amministrazione è il passaggio 3 dell'8.
  
![Diagramma di panoramica.](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Installare Skype for Business Server strumenti di amministrazione

Il supporto di installazione per Skype for Business Server offre un'esperienza flessibile. Quando si esegue Setup.exe per la prima volta, gli unici strumenti installati sono la Distribuzione guidata Skype for Business Server e Skype for Business Server Management Shell. Usando questi due strumenti, noti come componenti di base, è possibile continuare con il processo di installazione, ma non forniscono funzionalità principali per l'ambiente di Skype for Business Server complessivo. La Distribuzione guidata viene avviata automaticamente dopo l'installazione dei componenti di base. La sezione della Distribuzione guidata intitolata **Installa strumenti di amministrazione** installa Skype for Business Server Generatore di topologie e Skype for Business Server Pannello di controllo.
  
> [!IMPORTANT]
> In ogni ambiente Skype for Business Server deve essere installato almeno un server con gli strumenti di amministrazione. 
  
Guardare i passaggi video per **Installare gli strumenti di amministrazione**:
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Installare Skype for Business Server strumenti di amministrazione dalla Distribuzione guidata

1. Inserire il supporto di installazione Skype for Business Server. Se l'installazione non viene avviata automaticamente, fare doppio clic su **Imposta**.
    
2. Il supporto di installazione richiede Microsoft Visual C++ per l'esecuzione. Verrà visualizzata una finestra di dialogo che chiede se si vuole installarla. Fare clic su **Sì**.
    
3. Usando La configurazione intelligente, una nuova funzionalità in Skype for Business Server, è possibile connettersi a Internet per verificare la disponibilità di aggiornamenti durante il processo di installazione. Ciò offre un'esperienza migliore assicurandosi di avere gli aggiornamenti più recenti per il prodotto al momento dell'installazione. Fare clic su **Installa** per avviare l'installazione.
    
4. Esaminare attentamente il Contratto di licenza e, se si accetta, selezionare **Accetto le condizioni nel contratto di licenza** e fare clic su **OK**.
    
5. I componenti di base Skype for Business Server verranno installati nel server. 
    
    I componenti principali sono costituiti dagli elementi seguenti, come illustrato nella figura.
    
    ![Schermata Componenti di base nelle app.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype for Business Server Distribuzione guidata** Programma di distribuzione che fornisce una finestra di avvio per l'installazione dei vari componenti di Skype for Business Server.
    
   - **Skype for Business Server Management Shell** Programma PowerShell preconfigurato che consente l'amministrazione di Skype for Business Server.
    
     Al termine dell'installazione dei componenti di base, verrà avviata automaticamente la Distribuzione guidata Skype for Business Server, come illustrato nella figura. 
    
     ![distribuzione guidata Skype for Business Server.](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Oltre ai componenti di base, è anche necessario installare Skype for Business Server Generatore di topologie e Skype for Business Server Pannello di controllo in almeno un server nell'ambiente. Fare clic su **Installa strumenti di amministrazione** nella Distribuzione guidata.
    
7. Fare clic su **Avanti** per iniziare l'installazione.
    
8. Al termine dell'installazione, fare clic su **Fine**. Gli strumenti di amministrazione vengono ora aggiunti al server, come illustrato nella figura.
    
    ![Skype for Business Server strumenti di amministrazione.](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype for Business Server Generatore di topologie** Un programma usato per compilare, distribuire e gestire topologie.
    
   - **Skype for Business Server Pannello di controllo** Programma utilizzato per amministrare l'installazione.
    

