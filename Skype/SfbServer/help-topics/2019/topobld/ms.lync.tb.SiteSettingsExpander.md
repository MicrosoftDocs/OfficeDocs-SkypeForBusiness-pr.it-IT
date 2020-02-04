---
title: Espansione delle impostazioni per Lync Server Lite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per modificare le proprietà di un sito esistente, eseguire le operazioni seguenti:'
ms.openlocfilehash: 20c74cd3842137df5dce35647bdb5ad28b89b4e0
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687969"
---
# <a name="lync-server-site-settings-expander"></a>Espansione delle impostazioni per Lync Server Lite

Per modificare le proprietà di un sito esistente, eseguire le operazioni seguenti:



## <a name="site-properties"></a>Proprietà del sito

In proprietà sito è possibile modificare o modificare il nome del sito (obbligatorio), la descrizione (facoltativa), la città (facoltativa), lo stato/provincia (facoltativo) e il codice paese/area geografica (facoltativo).

Per informazioni dettagliate sulle proprietà del sito, vedere [aggiungere siti di succursale alla topologia](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).

## <a name="federation-route-properties"></a>Proprietà route federative

Per impostare un'assegnazione della route Federation del sito, è prima necessario che la Federazione sia abilitata in un server perimetrale o in un pool di Edge Server. Se la Federazione non è abilitata in un server perimetrale o in un pool, le impostazioni di assegnazione della route federativo per il sito non saranno disponibili per la modifica.

Se è stata configurata l'impostazione federativo in Edge Server o pool, selezionare **Abilita** a livello di sito. Selezionare quindi un bordo o un Director dall'elenco a discesa per impostare la route federativo.

> [!CAUTION]
> Questa impostazione avrà effetto su tutti i siti. Verificare che l'impostazione che si sta configurando in questo sito sia appropriata per tutti i siti.

## <a name="see-also"></a>Vedere anche

Per informazioni dettagliate, vedere [topologie per l'accesso degli utenti esterni](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).


