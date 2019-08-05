---
title: Expander per le impostazioni del registrar per Lync Server per 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Si modificano le impostazioni per la resilienza e si configurano le proprietà seguenti:'
ms.openlocfilehash: 5ed1311e73ea035b7672ba75bab337c9212e8816
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189437"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a>Expander per le impostazioni del registrar per Lync Server per 2010
 
Si modificano le impostazioni **** per la resilienza e si configurano le proprietà seguenti:
  
- Selezionare **pool di registrar di backup associato** dall'elenco.
    
    Facoltativamente, selezionare la casella **di controllo failover automatico e failback per la voce** .
    
    Configurare l' **intervallo di rilevamento errori vocali (sec)** e l' **intervallo di failback vocale (sec)**. Per impostazione predefinita, gli intervalli sono 120 secondi per il rilevamento dell'errore vocale e 240 secondi per il failback vocale.
    
    > [!CAUTION]
    > Il numero di secondi definiti per gli intervalli di failover e failback deve essere testato con attenzione per verificare che la resilienza funzioni come previsto. L'impostazione dell'intervallo su basso (ovvero meno di 120 secondi) o il failover e il failback impostati troppo da vicino può causare il failover effettivo e il failback non funzionano come previsto. 
  
  **OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.
  
  **Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.
  
  **Guida** Consente di visualizzare questa schermata della Guida.
  

