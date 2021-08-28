---
title: Pagina delle opzioni Installa database mirror
ms.reviewer: ''
ms.author: v-cichur
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
ms.openlocfilehash: 894ff38814ef2c50f3492216531db45246a67548
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599107"
---
# <a name="install-mirror-database-option-page"></a>Pagina delle opzioni Installa database mirror
 
È possibile configurare la sezione **Impostazioni database mirror** definendo le impostazioni seguenti:
  
- Digitare il **percorso della condivisione file** per definire il percorso per i file di backup SQL Server per il database di cui eseguire il mirroring.
    
    > [!NOTE]
    > L'SQL Server principale (istanza denominata o istanza predefinita) deve disporre delle autorizzazioni di scrittura per la condivisione file definita qui. L'SQL Server mirror (istanza denominata o istanza predefinita) deve disporre delle autorizzazioni di lettura per la stessa condivisione file. 
  
  **OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.
  
  **Annulla** Rimuove le modifiche e chiude la finestra di dialogo.
  
  **?** Visualizza questa schermata della Guida.
  
## <a name="see-also"></a>Vedere anche

[Distribuire SQL mirroring per la disponibilità elevata del server back-end in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
