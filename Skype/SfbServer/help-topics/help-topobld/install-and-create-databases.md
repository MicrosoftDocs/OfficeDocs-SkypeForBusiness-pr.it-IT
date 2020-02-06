---
title: Installare e creare database
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Selezionare i database che si desidera creare per la distribuzione. Per impostazione predefinita, il database verrà creato nel server SQL definito nel sito definito e distribuirà e configurerà automaticamente i file di database in base a SQL Server in cui si inseriscono i database.
ms.openlocfilehash: 72eebc4523eb538762adcfd3c2ee7138853a80ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819828"
---
# <a name="install-and-create-databases"></a>Installare e creare database

Selezionare i database che si desidera creare per la distribuzione. Per impostazione predefinita, il database verrà creato nel server SQL definito nel sito definito e distribuirà e configurerà automaticamente i file di database in base a SQL Server in cui si inseriscono i database.

 **Selezionare i database da creare**: selezionare la casella di controllo di tutti i database che si desidera distribuire e configurare. Selezionare la casella di controllo di uno o di tutti i database che si vuole distribuire.

> [!CAUTION]
> SQL Server deve essere già configurato per l'istanza (se disponibile) e le porte del firewall devono essere aperte per contenere l'istanza in cui si stanno distribuendo i database. Per informazioni dettagliate, vedere [configurare SQL Server per Lync server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)

 **Avanzate**: fare clic su SQL Server e fare clic sul pulsante **Avanzate** per scegliere le opzioni per i percorsi dei file di database in SQL Server. Per informazioni dettagliate sulla posizione avanzata dei file di database, vedere [installazione di database tramite Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)

 **Indietro**: se si fa clic su questo pulsante si ritorna alla schermata precedente (potrebbe non essere sempre disponibile, in base a come è arrivata la finestra di dialogo).

 **Avanti**: se si fa clic su questo pulsante si esegue il commit della selezione nella finestra di dialogo corrente e si passa alla finestra di dialogo successiva per la configurazione di altre informazioni

 **Annulla**: se si fa clic su questo pulsante si chiude la configurazione e si eliminano le modifiche. Alcuni, ma non tutte le schermate di configurazione, ti chiederanno se vuoi chiudere e annullare le modifiche. Selezionando **Sì** si chiuderà la configurazione corrente e si chiuderà la configurazione corrente e si tornerà a Generatore di topologie. Se si seleziona **No** , verrà visualizzata la finestra di dialogo configurazione corrente e si consentirà di continuare la configurazione.

 **Guida**: se si fa clic sul pulsante della **Guida** , vengono visualizzate le informazioni della Guida associate alla finestra di dialogo configurazione corrente.


