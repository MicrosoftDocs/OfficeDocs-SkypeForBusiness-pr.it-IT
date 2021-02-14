---
title: Installare gli strumenti di amministrazione in Skype for Business Server
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
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: "Riepilogo: informazioni su come installare gli strumenti di amministrazione necessari per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Centro di valutazione Microsoft all'indirizzo: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ."
ms.openlocfilehash: ab3e64ae5d330c5b24eff7c23172b1141ff75527
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812106"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Installare gli strumenti di amministrazione in Skype for Business Server
 
**Riepilogo:** Informazioni su come installare gli strumenti di amministrazione necessari per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Centro di valutazione Microsoft all'indirizzo: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
Gli strumenti di amministrazione includono Generatore di topologie e il Pannello di controllo. Gli strumenti di amministrazione devono essere installati in almeno un server della topologia o in una workstation di gestione a 64 bit che esegue una versione del sistema operativo Windows supportata per Skype for Business Server. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. È tuttavia necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come illustrato nel diagramma. L'installazione degli strumenti di amministrazione è il passaggio 3 di 8.
  
![Diagramma di panoramica](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Installare gli strumenti di amministrazione di Skype for Business Server

Il supporto di installazione per Skype for Business Server offre un'esperienza flessibile. Quando si esegue Setup.exe, gli unici strumenti installati sono la Distribuzione guidata di Skype for Business Server e Skype for Business Server Management Shell. Utilizzando questi due strumenti, noti come componenti di base, è possibile continuare con il processo di installazione, ma non forniscono funzionalità principali per l'ambiente generale di Skype for Business Server. La Distribuzione guidata viene avviata automaticamente dopo l'installazione dei componenti di base. Nella sezione della Distribuzione guidata intitolata **Installa** strumenti di amministrazione vengono installati Generatore di topologie di Skype for Business Server e il Pannello di controllo di Skype for Business Server.
  
> [!IMPORTANT]
> In ogni ambiente Skype for Business Server deve essere installato almeno un server in cui sono installati gli strumenti di amministrazione. 
  
Guardare i passaggi video per installare **gli strumenti di amministrazione:**
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Installare gli strumenti di amministrazione di Skype for Business Server dalla Distribuzione guidata

1. Inserire il supporto di installazione di Skype for Business Server. Se l'installazione non viene avviata automaticamente, fare doppio clic su **Setup.**
    
2. Il supporto di installazione richiede l'esecuzione di Microsoft Visual C++. Verrà visualizzata una finestra di dialogo in cui viene chiesto se si desidera installarla. Fare clic su **Sì**.
    
3. Utilizzando Smart Setup, una nuova funzionalità di Skype for Business Server, è possibile connettersi a Internet per verificare la disponibilità di aggiornamenti durante il processo di installazione. In questo modo è possibile ottenere un'esperienza migliore assicurando di disporre degli aggiornamenti più recenti per il prodotto al momento dell'installazione. Fare clic su **Installa** per avviare l'installazione.
    
4. Esaminare attentamente il Contratto di Licenza e, se si accetta, selezionare Accetto i termini del contratto di **licenza** e fare clic su **OK.**
    
5. I componenti di base di Skype for Business Server verranno installati nel server. 
    
    I componenti di base sono costituiti da quanto segue, come illustrato nella figura.
    
    ![Schermata Componenti di base nelle app.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Distribuzione guidata di Skype for Business Server** Programma di distribuzione che fornisce una finestra di avvio per l'installazione dei vari componenti di Skype for Business Server.
    
   - **Skype for Business Server Management Shell** Programma PowerShell preconfigurato che consente l'amministrazione di Skype for Business Server.
    
     Al termine dell'installazione dei componenti di base, verrà avviata automaticamente la Distribuzione guidata di Skype for Business Server, come illustrato nella figura. 
    
     ![Distribuzione guidata di Skype for Business Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Oltre ai componenti di base, è inoltre necessario installare Generatore di topologie di Skype for Business Server e il Pannello di controllo di Skype for Business Server in almeno un server nell'ambiente. Fare **clic su Installa strumenti di** amministrazione nella Distribuzione guidata.
    
7. Fare clic su **Avanti** per iniziare l'installazione.
    
8. Al termine dell'installazione, fare clic su **Fine.** Gli strumenti di amministrazione vengono ora aggiunti al server, come illustrato nella figura.
    
    ![Strumenti di amministrazione di Skype for Business Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Generatore di** topologie di Skype for Business Server Programma utilizzato per creare, distribuire e gestire topologie.
    
   - **Pannello di controllo di Skype for Business Server** Programma utilizzato per amministrare l'installazione.
    

