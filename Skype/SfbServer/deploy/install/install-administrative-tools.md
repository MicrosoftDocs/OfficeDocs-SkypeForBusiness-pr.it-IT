---
title: Installare gli strumenti di amministrazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: "Riepilogo: informazioni su come installare gli strumenti amministrativi necessari per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Microsoft Evaluation Center all' https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverIndirizzo:."
ms.openlocfilehash: 3abf2eb35a4593f25db75e175f3cd30fdf49e21b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790174"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Installare gli strumenti di amministrazione in Skype for Business Server
 
**Riepilogo:** Informazioni su come installare gli strumenti di amministrazione necessari per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Microsoft Evaluation Center all' [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Indirizzo:.
  
Gli strumenti di amministrazione includono generatore di topologie e il pannello di controllo. Gli strumenti di amministrazione devono essere installati in almeno un server della topologia o in una workstation di gestione a 64 bit in cui è in esecuzione una versione del sistema operativo Windows supportata per Skype for Business Server. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 in ordine e dopo i passaggi da 1 a 5, come illustrato nel diagramma. L'installazione degli strumenti di amministrazione è il passaggio 3 di 8.
  
![Diagramma di panoramica](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Installare gli strumenti di amministrazione di Skype for Business Server

Il supporto di installazione per Skype for Business Server offre un'esperienza flessibile. La prima volta che si esegue Setup. exe, gli unici strumenti installati sono la distribuzione guidata di Skype for Business Server e Skype for Business Server Management Shell. Usando questi due strumenti, noti come componenti principali, puoi continuare con il processo di installazione, ma non fornisci funzionalità principali per l'ambiente globale di Skype for Business Server. La distribuzione guidata viene avviata automaticamente dopo l'installazione dei componenti principali. La sezione della distribuzione guidata intitolata **Install Administrative Tools** installa il generatore di topologia di Skype for Business Server e il pannello di controllo di Skype for Business Server.
  
> [!IMPORTANT]
> Ogni ambiente di Skype for Business Server deve avere almeno un server con gli strumenti di amministrazione installati. 
  
Guardare la procedura video per **installare gli strumenti di amministrazione**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Installare gli strumenti di amministrazione di Skype for Business Server dalla distribuzione guidata

1. Inserire il supporto di installazione di Skype for Business Server. Se l'installazione non viene avviata automaticamente, fare doppio clic su **configurazione**.
    
2. Il supporto di installazione richiede l'esecuzione di Microsoft Visual C++. Verrà visualizzata una finestra di dialogo che chiede se si vuole installarla. Fare clic su **Sì**.
    
3. Usando la configurazione intelligente, una nuova funzionalità di Skype for Business Server è possibile connettersi a Internet per verificare la disponibilità di aggiornamenti durante il processo di installazione. Questo offre un'esperienza migliore assicurandosi di avere gli aggiornamenti più recenti al prodotto durante l'installazione. Fare clic su **Installa** per avviare l'installazione.
    
4. Esaminare attentamente il contratto di licenza e, se si è d'accordo, selezionare **Accetto i termini del contratto di licenza**e fare clic su **OK**.
    
5. I componenti principali di Skype for Business Server verranno installati nel server. 
    
    I componenti principali sono i seguenti, come illustrato nella figura.
    
    ![Componenti principali nella schermata delle app.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Distribuzione guidata di Skype for Business Server** Un programma di distribuzione che fornisce una piattaforma di avvio per l'installazione dei vari componenti di Skype for Business Server.
    
   - **Skype for Business Server Management Shell** Programma di PowerShell preconfigurato che consente l'amministrazione di Skype for Business Server.
    
     Una volta completata l'installazione dei componenti principali, verrà avviata automaticamente la distribuzione guidata di Skype for Business Server, come illustrato nella figura. 
    
     ![Distribuzione guidata di Skype for Business Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Oltre ai componenti principali, dovrai installare anche il generatore di topologia di Skype for Business Server e il pannello di controllo di Skype for Business Server in almeno un server nell'ambiente. Fare clic su **installa strumenti di amministrazione** nella distribuzione guidata.
    
7. Fare clic su **Avanti** per avviare l'installazione.
    
8. Dopo aver completato l'installazione, fare clic su **fine**. Gli strumenti di amministrazione vengono ora aggiunti al server, come illustrato nella figura.
    
    ![Strumenti di amministrazione di Skype for Business Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Generatore di topologia di Skype for Business Server** Programma usato per compilare, distribuire e gestire le topologie.
    
   - **Pannello di controllo di Skype for Business Server** Programma usato per amministrare l'installazione.
    

