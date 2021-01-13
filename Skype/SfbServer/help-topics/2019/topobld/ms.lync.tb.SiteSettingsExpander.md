---
title: Espansione delle impostazioni del sito di Lync Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per modificare le proprietà di un sito esistente, eseguire le operazioni seguenti:'
ms.openlocfilehash: 30e11a6b580b80719ffd6f745c7c37edf2cf358e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805566"
---
# <a name="lync-server-site-settings-expander"></a>Espansione delle impostazioni del sito di Lync Server

Per modificare le proprietà di un sito esistente, eseguire le operazioni seguenti:



## <a name="site-properties"></a>Proprietà del sito

Nelle proprietà del sito è possibile cambiare o modificare il nome del sito (obbligatorio), la descrizione (facoltativa), la città (facoltativa), la provincia (facoltativa) e il codice paese/area geografica (facoltativo).

Per informazioni dettagliate sulle proprietà di un sito, vedere [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).

## <a name="federation-route-properties"></a>Proprietà della route di federazione

Per impostare un'assegnazione di route di federazione per il sito, è necessario innanzitutto che in un server perimetrale o in un pool di server perimetrali sia abilitata la federazione. In caso contrario, le impostazioni di assegnazione della route di federazione per il sito non saranno disponibili per la modifica.

Se l'impostazione di federazione è stata configurata nel server perimetrale o nel pool di server perimetrali, selezionare **Abilita** a livello di sito. Selezionare quindi nell'elenco a discesa un server perimetrale o un server Director da impostare come route di federazione.

> [!CAUTION]
> Questa impostazione avrà effetto su tutti i siti. Accertarsi quindi che l'impostazione da configurare per questo sito sia appropriata per tutti i siti.

## <a name="see-also"></a>Vedere anche

Per informazioni dettagliate, vedere [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).


