---
title: Espansione delle impostazioni del sito di Lync Server
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
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Per modificare le proprietà di un sito esistente, eseguire le operazioni seguenti:'
ms.openlocfilehash: 9ace8cc0975e971e7f3c3fe55c89324330816f62d78b0ee5c9b23d16e9ff9689
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305468"
---
# <a name="lync-server-site-settings-expander"></a>Espansione delle impostazioni del sito di Lync Server

Per modificare le proprietà di un sito esistente, eseguire le operazioni seguenti:



## <a name="site-properties"></a>Proprietà del sito

Nelle proprietà del sito è possibile cambiare o modificare il nome del sito (obbligatorio), la descrizione (facoltativa), la città (facoltativa), la provincia (facoltativa) e il codice paese/area geografica (facoltativo).

Per informazioni dettagliate sulle proprietà di un sito, vedere [Add Branch Sites to Your Topology](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology).

## <a name="federation-route-properties"></a>Proprietà della route di federazione

Per impostare un'assegnazione di route di federazione per il sito, è necessario innanzitutto che in un server perimetrale o in un pool di server perimetrali sia abilitata la federazione. In caso contrario, le impostazioni di assegnazione della route di federazione per il sito non saranno disponibili per la modifica.

Se l'impostazione di federazione è stata configurata nel server perimetrale o nel pool di server perimetrali, selezionare **Abilita** a livello di sito. Selezionare quindi nell'elenco a discesa un server perimetrale o un server Director da impostare come route di federazione.

> [!CAUTION]
> Questa impostazione avrà effetto su tutti i siti. Accertarsi quindi che l'impostazione da configurare per questo sito sia appropriata per tutti i siti.

## <a name="see-also"></a>Vedere anche

Per informazioni dettagliate, vedere [Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access).