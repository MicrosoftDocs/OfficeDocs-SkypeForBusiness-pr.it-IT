---
title: Installare prerequisiti per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: "Riepilogo: informazioni sui server e sui ruoli del server che è necessario configurare prima di installare Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Microsoft Evaluation Center all' https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverIndirizzo:."
ms.openlocfilehash: 2fbf90a1ee6f517cad2c716e6a50dd814352993e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240908"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Installare prerequisiti per Skype for Business Server
 
**Riepilogo:** Informazioni sui server e i ruoli del server che è necessario configurare prima di installare Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
L'installazione dei prerequisiti consiste nella configurazione di Windows Server installando i ruoli e le funzionalità necessari in ognuno dei server della topologia. I requisiti si basano sul ruolo che il server eseguirà nella topologia. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 in ordine e dopo i passaggi da 1 a 5, come illustrato nel diagramma. L'installazione dei prerequisiti è il passaggio 1 di 8.
  
![Diagramma di panoramica-installare i prerequisiti.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Configurazione di Windows Server

Skype for Business Server richiede il sistema operativo Windows Server e un certo numero di prerequisiti prima che possa essere installato. Per informazioni dettagliate sulla pianificazione dei prerequisiti, vedere [requisiti del server per Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  
> [!TIP]
> Questa procedura usa Windows Server 2012 R2. Se si usa una versione diversa di Windows Server, la procedura potrebbe essere leggermente diversa. 
  
> [!IMPORTANT]
> Prima di iniziare, verificare che Windows Server sia aggiornato tramite Windows Update. 
  
![Windows Server aggiornato.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Guardare la procedura video per **installare i prerequisiti**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Installare i ruoli e le funzionalità necessari per i server front-end

È possibile installare i ruoli e le funzionalità necessari tramite Server Manager. 
    
1. Installare le caratteristiche software prerequisiti elencate nei [requisiti del server per Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). Il software necessario deve essere installato nel server che eseguirà Skype for Business Server.
    
    > [!CAUTION]
    > Windows Server 2012 R2 non installa tutti i file di origine per le caratteristiche necessarie per impostazione predefinita. Se il server non è connesso a Internet, sarà necessario inserire il supporto di Windows Server 2012 R2 e selezionare **specificare un percorso di origine alternativo** per installare le caratteristiche necessarie. I file di origine si trovano nella directory sources\sxs. Ad esempio, se il contenuto multimediale di Windows Server 2012 R2 è nell'unità D, devi impostare il percorso `d:\sources\sxs`. È importante avere gli aggiornamenti più recenti di Windows Update. Se non si è connessi a Internet, sarà necessario installare manualmente tutti gli aggiornamenti pertinenti e i prerequisiti per gli aggiornamenti necessari. 
  
1. Quando la finestra di dialogo indica che l'installazione è stata completata, sarà necessario riavviare il server per completare il processo.
    
1. Eseguire di nuovo **Windows Update** per verificare la presenza di aggiornamenti per i ruoli e i servizi installati.
    
1. Se si usa il pannello di controllo di Skype for Business Server su questo server, è necessario installare anche Silverlight. Per installare Silverlight, vedere [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> I prerequisiti per i server che eseguono ruoli diversi da server front-end, ad esempio il ruolo di Director, la chat persistente o Edge, hanno i loro prerequisiti. Per informazioni dettagliate sui prerequisiti esatti richiesti da ogni tipo di server, vedere requisiti del server [per Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  

