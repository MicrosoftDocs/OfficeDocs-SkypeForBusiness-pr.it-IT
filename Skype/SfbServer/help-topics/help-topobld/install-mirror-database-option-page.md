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
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: 'È possibile configurare la sezione Impostazioni database mirror definendo le impostazioni seguenti:'
ms.openlocfilehash: 63e3795cc52b9b8e3601b2260df253fdcd2d9c59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806896"
---
# <a name="install-mirror-database-option-page"></a>Pagina delle opzioni Installa database mirror
 
È possibile configurare la sezione **Impostazioni database mirror** definendo le impostazioni seguenti:
  
- Digitare il **percorso della condivisione file** per definire il percorso dei file di SQL Server di backup per il database in cui si sta facendo il mirroring.
    
    > [!NOTE]
    > L'istanza di SQL Server primaria (istanza denominata o istanza predefinita) deve disporre di autorizzazioni di scrittura per la condivisione file definita in questo percorso. L'istanza di SQL Server mirror (istanza denominata o istanza predefinita) deve disporre delle autorizzazioni di lettura per la stessa condivisione file. 
  
  **OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.
  
  **Annulla** Rimuove le modifiche e chiude la finestra di dialogo.
  
  **?** Visualizza questa schermata della Guida.
  
## <a name="see-also"></a>Vedere anche

[Distribuire il mirroring di SQL per la disponibilità elevata del server back-end in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
