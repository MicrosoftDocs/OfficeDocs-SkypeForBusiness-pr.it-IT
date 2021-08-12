---
title: Espansione delle impostazioni del servizio di registrazione per Lync Server per la versione 2010
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
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'È possibile modificare le impostazioni della sezione Resilienza e configurare le proprietà seguenti:'
ms.openlocfilehash: 9c397f3d08bd99b477f5c0568aa62938e59cdf6416e5c5ccfbe5771465c86012
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280999"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a>Espansione delle impostazioni del servizio di registrazione per Lync Server per la versione 2010
 
È possibile modificare le impostazioni relative alla **Resilienza** e configurare le proprietà seguenti:
  
- Selezionare **Pool di registrazione di backup associato** dall'elenco.
    
    Se lo si desidera, selezionare la casella di controllo **Failover e failback automatico per VolP**.
    
    Configurare le opzioni **Intervallo rilevamento errori VolP (sec)** e **Intervallo failback VolP (sec)**. Per impostazione predefinita, gli intervalli sono di 120 secondi per il rilevamento errori VolP e di 240 secondi per il failback VolP.
    
    > [!CAUTION]
    > Il numero di secondi definito per gli intervalli di failover e failback deve essere testato attentamente per assicurare che la resilienza funzioni nel modo previsto. L'impostazione di un intervallo troppo basso, ovvero inferiore a 120 secondi, o l'impostazione di valori di failover e failback troppo vicini potrebbe compromettere il funzionamento del failover e del failback. 
  
  **OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.
  
  **Annulla** Rimuove le modifiche e chiude la finestra di dialogo.
  
  **?** Visualizza questa schermata della Guida.
  

