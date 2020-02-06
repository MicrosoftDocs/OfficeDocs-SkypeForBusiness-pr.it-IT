---
title: Creare una condivisione file in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
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
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: "Riepilogo: informazioni su come creare una condivisione file di Windows Server come parte dell'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Microsoft Evaluation Center all' https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverIndirizzo:."
ms.openlocfilehash: 57d1bc348d1fed7a0dc8297723d41d3d90888710
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790184"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Creare una condivisione file in Skype for Business Server
 
**Riepilogo:** Informazioni su come creare una condivisione file di Windows Server come parte dell'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Microsoft Evaluation Center all'[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Indirizzo:.
  
Skype for Business Server richiede una condivisione file in modo che i computer di tutta la topologia possano scambiare file. La creazione di una condivisione file è il passaggio 2 di 8 nel processo di installazione di Skype for Business Server. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 in ordine e dopo i passaggi da 1 a 5 come indicato nel diagramma. Per informazioni sulla pianificazione della condivisione file, vedere [requisiti ambientali per i requisiti di Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o server [per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Diagramma di panoramica](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Creare una condivisione di file di base

Questa sezione illustra la creazione di una condivisione di file di Windows Server di base. È supportata una condivisione file di base di Windows Server con Skype for Business Server. Tuttavia, non garantisce in modo esplicito una disponibilità elevata. Per un ambiente ad alta disponibilità, è consigliabile una condivisione file del file System distribuito (DFS). Per altre informazioni su una condivisione di file ad alta disponibilità e su DFS, vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Windows Server 2012 R2 ha compiuto notevoli salti nella fornitura di soluzioni di condivisione file di tipo SAN (Storage Area Network) con la piattaforma Windows Server. Rispetto a un dispositivo tradizionale basato su SAN, una soluzione di archiviazione di Windows Server 2012 R2 può ridurre i costi a metà con un impatto molto minimo sulle prestazioni. Per altre informazioni sulle opzioni di condivisione file in Windows Server 2012 R2, vedere lo spazio di archiviazione scaricabile white paper [Windows server 2012 R2](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf). 
  
Guardare la procedura video per **creare una condivisione file**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>Creare una condivisione di file di base

1. Accedere al computer in cui verrà ospitata la condivisione file.
    
2. Fare clic con il pulsante destro del mouse sulla cartella che si prevede di condividere e scegliere **Proprietà**.
    
3. Selezionare la scheda **condivisione** e fare clic su **condivisione avanzata**.
    
4. Fare clic su **Condividi cartella**.
    
5. Fare clic su **autorizzazioni**.
    
6. Aggiungere il gruppo **Administrators** locale del server che ospita la condivisione file, concedere **Consenti: controllo completo, modifica e** diritti di lettura e quindi fare clic su **OK**.
    
7. Fare di nuovo clic su **OK** e prendere nota del percorso di rete.
    
8. Fare clic su **fine** per chiudere la procedura guidata.
    
     ![Scheda condivisione per la condivisione di una cartella.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>Se l'archivio file è ospitato in una condivisione DFS, verrà ricevuto l'avviso seguente:

Avviso: non è possibile accedere alle autorizzazioni di\\<domain>\<condivisione per "Condividi>".

>Questa operazione è prevista se non si è un amministratore nel file server o se si tratta di una condivisione di file System distribuito (DFS). Se le autorizzazioni di condivisione sono già state configurate, questo avviso può essere ignorato. Se si tratta di una nuova condivisione, vedere la documentazione per informazioni dettagliate sulla configurazione manuale delle autorizzazioni di condivisione.

>A causa dell'impossibilità di accedere alle autorizzazioni di condivisione per una condivisione DFS, Skype for Business Server non sarà in grado di impostare esplicitamente i gruppi sulla condivisione file. Per assicurarti che i componenti di Skype for Business Server possano accedere alla condivisione file con le autorizzazioni appropriate, assicurati che i gruppi RTC seguenti vengano aggiunti con le autorizzazioni leggi e cambia livello di condivisione oltre agli amministratori locali con la condivisione di controllo completo autorizzazioni.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
