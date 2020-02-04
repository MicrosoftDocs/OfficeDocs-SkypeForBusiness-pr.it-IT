---
title: Pagina Installare opzioni di database
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Si configurano le opzioni avanzate per la posizione dei file di database e di log in SQL Server. Le opzioni disponibili sono:'
ms.openlocfilehash: 6725c85ee8ccd755e1846f2e2030fd4cab4c5f22
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688429"
---
# <a name="install-database-options-page"></a>Pagina Installare opzioni di database

Si configurano le opzioni avanzate per la posizione dei file di database e di log in SQL Server. Le opzioni disponibili sono:

> [!IMPORTANT]
> Selezionare l'opzione più adatta alle proprie esigenze e ai criteri relativi ai dati e alla posizione del file di log nei computer SQL Server.

 **Determinare automaticamente la posizione del file di database**: l'opzione predefinita usa un algoritmo che determina lo spazio disponibile in SQL Server e distribuisce il database e i file di log per ottenere prestazioni ottimali.

 **Usare le impostazioni predefinite dell'istanza di SQL Server**: selezionare questa opzione per inserire file di database e file di log in base alle opzioni di istanza in SQL Server. Le opzioni sono in genere gestite e configurate dall'amministratore del database.

 **Noi questi path in SQL Server di destinazione**: selezionare questa opzione per definire i percorsi personalizzati per i file di database e di log di SQL Server digitando il percorso completo dell'unità e della cartella in cui verranno inseriti i file di database e di log.

> [!IMPORTANT]
> I percorsi immessi possono essere modificati in base agli algoritmi di ottimizzazione delle prestazioni nell'installazione. Per informazioni dettagliate, vedere [installazione di database tramite Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).

 **OK**: fare clic sul pulsante OK per eseguire il commit delle modifiche.

 **Annulla**: fare clic su Annulla per annullare le modifiche e tornare alla schermata Installa database.

 **Guida**: fare clic sul pulsante della Guida per accedere alla pagina della guida.

## <a name="see-also"></a>Vedere anche

[Inserimento di dati e file di log di SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
