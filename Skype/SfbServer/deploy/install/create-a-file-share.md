---
title: Creare una condivisione file in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: "Riepilogo: informazioni su come creare una condivisione file di Windows Server come parte dell'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Centro di valutazione Microsoft all'indirizzo: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ."
ms.openlocfilehash: 63ed4c54154698336bea7adb87db4e81d5fd35b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812236"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Creare una condivisione file in Skype for Business Server
 
**Riepilogo:** Informazioni su come creare una condivisione file di Windows Server come parte dell'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Centro di valutazione Microsoft all'indirizzo: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
Skype for Business Server richiede una condivisione file in modo che i computer in tutta la topologia possano scambiare file. La creazione di una condivisione file è il passaggio 2 di 8 del processo di installazione di Skype for Business Server. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. È tuttavia necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5 come illustrato nel diagramma. Per informazioni dettagliate sulla condivisione file, vedere Requisiti ambientali per i requisiti di [Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o Server per Skype for Business Server [2019.](../../../SfBServer2019/plan/system-requirements.md)
  
![Diagramma di panoramica](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Creare una condivisione file di base

In questa sezione viene illustrata la creazione di una condivisione file di base di Windows Server. Una condivisione file di base di Windows Server è supportata con Skype for Business Server. Tuttavia, non fornisce in modo esplicito la disponibilità elevata. Per un ambiente a disponibilità elevata, è consigliabile una condivisione file DFS (Distributed File System). Per ulteriori informazioni su una condivisione file a disponibilità elevata e DFS, vedere Pianificare la disponibilità elevata e il ripristino di emergenza [in Skype for Business Server.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
> [!NOTE]
> Windows Server 2012 R2 ha fatto grandi passi in avanti nella fornitura di soluzioni di condivisione file di tipo SAN (Storage Area Network) tramite la piattaforma Windows Server. Rispetto a un'appliance tradizionale basata su SAN, una soluzione di archiviazione di Windows Server 2012 R2 può ridurre i costi dimezzi con un impatto minimo sulle prestazioni. Per ulteriori informazioni sulle opzioni di condivisione file in Windows Server 2012 R2, vedere il white paper scaricabile [Windows Server 2012 R2 Storage.](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf) 
  
Guardare i passaggi video per **creare una condivisione file:**
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>Creare una condivisione file di base

1. Accedere al computer che ospiterà la condivisione file.
    
2. Fare clic con il pulsante destro del mouse sulla cartella che si intende condividere e scegliere **Proprietà.**
    
3. Selezionare la **scheda Condivisione** e fare clic su **Condivisione avanzata.**
    
4. Fare **clic su Condividi questa cartella.**
    
5. Fare clic su **Autorizzazioni**.
    
6. Aggiungere il gruppo **Administrators** locale del server che ospita la condivisione file, concedere i diritti Consenti: Controllo **completo, Modifica** e Lettura e quindi fare clic su **OK.**
    
7. Fare **di nuovo** clic su OK e prendere nota del percorso di rete.
    
8. Fare **clic su** Fine per chiudere la procedura guidata.
    
     ![Scheda Condivisione per la condivisione di una cartella.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>Se l'archivio file è ospitato in una condivisione DFS, verrà ricevuto l'avviso seguente:

Avviso: impossibile accedere alle autorizzazioni di condivisione per " \\ <domain> \<share> ".

>Ciò è previsto se non si è un amministratore nel file server o se si tratta di una condivisione DFS (Distributed File System). Se le autorizzazioni di condivisione sono già state configurate, questo avviso può essere ignorato. Se si tratta di una nuova condivisione, fare riferimento alla documentazione per informazioni dettagliate sulla configurazione manuale delle autorizzazioni di condivisione.

>A causa dell'impossibilità di accedere alle autorizzazioni di condivisione in una condivisione DFS, Skype for Business Server non sarà in grado di impostare esplicitamente i gruppi nella condivisione file. Per assicurarsi che i componenti di Skype for Business Server possano accedere alla condivisione file con le autorizzazioni appropriate, assicurarsi che i seguenti gruppi RTC siano aggiunti con autorizzazioni di condivisione di livello lettura e modifica oltre agli amministratori locali con autorizzazioni di condivisione Controllo completo.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
