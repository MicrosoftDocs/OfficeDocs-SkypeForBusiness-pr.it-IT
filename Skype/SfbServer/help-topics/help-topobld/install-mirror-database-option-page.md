---
title: Pagina delle opzioni Installa database mirror
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: 'È possibile configurare la sezione Impostazioni database mirror definendo le impostazioni seguenti:'
ms.openlocfilehash: cfd32d4316bae824c0510f6ff921426dd161597c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775036"
---
# <a name="install-mirror-database-option-page"></a>Pagina delle opzioni Installa database mirror
 
È possibile configurare la sezione **Impostazioni database mirror** definendo le impostazioni seguenti:
  
- Digitare il **percorso della condivisione file** per definire il percorso per il backup SQL Server file per il database di cui viene eseguito il mirroring.
    
    > [!NOTE]
    > L'SQL Server principale (istanza denominata o istanza predefinita) deve disporre delle autorizzazioni di scrittura per la condivisione file definita qui. L'SQL Server mirror (istanza denominata o istanza predefinita) deve disporre delle autorizzazioni di lettura per la stessa condivisione file. 
  
  **OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.
  
  **Annulla** Rimuove le modifiche e chiude la finestra di dialogo.
  
  **?** Visualizza questa schermata della Guida.
  
## <a name="see-also"></a>Vedere anche

[Distribuire SQL mirroring per la disponibilità elevata del server back-end in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
