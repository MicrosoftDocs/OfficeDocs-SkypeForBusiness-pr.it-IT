---
title: Distribuire il ruolo del server VIS in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Riepilogo: distribuire il ruolo ViS (Video Interop Server) in Skype for Business Server.'
ms.openlocfilehash: 0683a413b3442cf09d2703d3593851c2808146a077df23969c339d526b9ebda8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330530"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a>Distribuire il ruolo del server VIS in Skype for Business Server
 
**Riepilogo:** Distribuire il ruolo Video Interop Server (VIS) in Skype for Business Server.
  
Per configurare il servizio VIS nel server appena creato in Generatore di topologie, avviare la distribuzione guidata di Skype for Business Server, premere **Install or Update Skype for Business Server System** ed eseguire la procedura seguente nella procedura guidata:
  
1.  Selezionare **Installa archivio di configurazione locale.**
    
2. Selezionare **Setup o Remove Skype for Business Server Components**.
    
3. Selezionare **Richiedi, Installa o Assegna certificati**.
    
4. Selezionare **Avvia servizi**.
    
Il software per questo servizio è ora installato e in esecuzione. È possibile aprire lo strumento mmc Servizi per verificare se **il servizio Skype for Business Server Video Interop Server** è in esecuzione insieme ad altri Skype for Business Server servizi. Successivamente, è necessario configurare il server o il pool VIS.
## <a name="see-also"></a>Vedere anche

[Configurare Video Interop Server in Skype for Business Server](configure-the-vis.md)
