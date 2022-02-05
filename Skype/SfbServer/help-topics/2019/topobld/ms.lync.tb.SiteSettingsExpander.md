---
title: Espansione delle impostazioni del sito di Lync Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Per modificare le proprietà di un sito esistente, eseguire le operazioni seguenti:'
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