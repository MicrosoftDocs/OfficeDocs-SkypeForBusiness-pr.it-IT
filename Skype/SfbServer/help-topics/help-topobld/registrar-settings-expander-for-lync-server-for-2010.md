---
title: Espansione delle impostazioni del servizio di registrazione per Lync Server per la versione 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 4271203bf9f737034796cc3b74c95836480df521
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217177"
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
  

