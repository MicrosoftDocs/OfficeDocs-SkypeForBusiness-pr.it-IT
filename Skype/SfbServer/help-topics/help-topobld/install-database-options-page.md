---
title: Pagina delle opzioni Installa database
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
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 'È possibile configurare le opzioni avanzate per il posizionamento dei file di database e di registro in SQL Server. Le opzioni disponibili sono:'
ms.openlocfilehash: 4c8c456aa1fd0e9eee150e184b4d1f7934c26b65
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215307"
---
# <a name="install-database-options-page"></a>Pagina delle opzioni Installa database

È possibile configurare le opzioni avanzate per il posizionamento dei file di database e di registro in SQL Server. Le opzioni disponibili sono:

> [!IMPORTANT]
> Selezionare l'opzione più adatta alle esigenze e ai criteri relativi ai dati e al posizionamento dei file di registro nei computer SQL Server.

 **Determina automaticamente il percorso dei file di database**: l'opzione predefinita utilizza un algoritmo che determina lo spazio disponibile su SQL Server e distribuisce il database e i file di registro per ottenere prestazioni ottimali.

 **Utilizzo dei valori predefiniti dell'istanza di SQL Server**: selezionare questa opzione per inserire file di registro e file di database in base alle impostazioni dell'istanza di SQL Server. Le opzioni vengono in genere gestite e configurate dall'amministratore del database.

 **Noi questi percorso su SQL Server di destinazione**: selezionare questa opzione per definire i propri percorsi per i file di database e di registro di SQL Server digitando il percorso completo dell'unità e della cartella in cui verranno inseriti i file di database e di registro.

> [!IMPORTANT]
> I percorsi immessi possono essere modificati in base agli algoritmi di ottimizzazione delle prestazioni nell'installazione. Per informazioni dettagliate, vedere [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).

 **OK**: fare clic su OK per eseguire il commit delle modifiche.

 **Annulla**: fare clic su Annulla per rimuovere le modifiche e tornare alla schermata Installa database.

 **?**: fare clic su ? per accedere a questa pagina della Guida.

## <a name="see-also"></a>Vedere anche

[Posizionamento dei file di registro e dei file di dati di SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
