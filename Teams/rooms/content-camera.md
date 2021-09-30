---
title: Informazioni su come configurare fotocamere contenuto - Microsoft Teams
ms.author: serdars
author: serdarsoysal
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
description: Usare una fotocamera del contenuto in una Microsoft Teams room, che interagisce con il software di elaborazione delle immagini per consentire ai relatori di disegnare su una lavagna analogica.
ms.openlocfilehash: 61c0a1a36630fa31190e57de08379d6e80321a34
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013160"
---
# <a name="content-cameras"></a>Videocamere di contenuto

Ora è possibile usare una fotocamera del contenuto con un Microsoft Teams room. Una fotocamera del contenuto interagisce con uno speciale software di elaborazione delle immagini e una lavagna per consentire a un relatore di disegnare su una lavagna analogica e condividere il contenuto con partecipanti remoti.

Vedere il video seguente per esempi di funzionalità della fotocamera del contenuto.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a>Configurare una fotocamera del contenuto

> [!NOTE]
> Rispettare sempre il codice dell'edificio del paese o dell'area, che può definire una distanza minima dal pavimento o un requisito che le apparecchiature a soffitto siano protette con una trave o un'altra struttura. Seguire le istruzioni di montaggio per l'hardware fornito con la fotocamera selezionata. I kit di montaggio della fotocamera OEM includono una fotocamera, gli estensori USB 2.0 e il cablaggio richiesto.

Le dimensioni della lavagna usata per la condivisione influiscono sulla posizione della fotocamera. I consigli per le dimensioni della bacheca sono:

- Larghezza da 0,9 a 1,8 m - Supportata
- Larghezza da 1,8 a 2,7 m - Scelta consigliata
- Larghezza di 2,7–3,6 m - Supportata
- Larga 3,6 metri, la fotocamera copre 2,7-3,6 metri e ritaglia il resto.

## <a name="camera-location"></a>Posizione della fotocamera

La posizione ideale di una fotocamera contenuto è centrata verticalmente e orizzontalmente sulla lavagna. I codici di edificio locali possono avere restrizioni di altezza che richiedono che la fotocamera sia elevata più in alto rispetto alla parte superiore della lavagna.

È possibile installare la fotocamera fino a 6 in. (152 mm) superiore alla parte superiore della lavagna e centrata sulla lavagna bianca come illustrato. Assicurati che l'immagine della fotocamera includa almeno 6 in. bordo (152 mm) su entrambi i lati orizzontalmente. È possibile usare l'anteprima della fotocamera nell'app Microsoft Teams Rooms per determinare il posizionamento finale della fotocamera.

![Diagramma di posizionamento della fotocamera del contenuto.](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a>Distanze della fotocamera

Usando i tipici indicatori della lavagna, l'esperienza utente remota ottimale è condividere i tratti input penna nell'intervallo di 1-2 mm per pixel nell'immagine della fotocamera del contenuto e i risultati migliori usano 1,5 mm per pixel. Tutte le fotocamere supportate offrono una risoluzione 1920 x 1080 e alcune possono superare tale risoluzione.

La distanza della fotocamera dalla lavagna si combina con la risoluzione della fotocamera e l'HFoV per determinare la distanza dalla lavagna. La tabella seguente mostra esempi di distanze per varie dimensioni della lavagna. È possibile usare questi valori come punti di partenza per determinare la posizione finale della fotocamera del contenuto.

**Distanza della fotocamera dalla lavagna**

| Fotocamera HFoV |0,91 m     | 1,8 m    | 2,74 m        |12 ft.  (3,65 m)         | Distanza massima da Whiteboard  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| 80°         | 0,54 m | 1,09 m  | 1,6 m    |2,17 m |2,28 m |
| 90°         | 0,45 m | 0,91 m   | 1,37 m    |1,82 m    |1,92 m |
| 100°        | 0,38 m| 0,77 m   | 1,15 m   |1,53 m   |1,61 m |
| 110°        | 0,32 m| 0,64 m   | 0,96 m   |1,28 m    |1,31 m |
| 120°        | 0,26 m| 0,52 m   | 0,79 m   |1,05 m   |1,10 m |
             

La distanza tra la fotocamera del contenuto e il muro su cui è montata la lavagna dipende dall'HFoV del modello di fotocamera, che varia. Installare fotocamere con un HFoV più grande (ad esempio 120 gradi) più vicino al muro e fotocamere con un HFoV più stretto più lontano dal muro. Controllare l'HFoV prima di iniziare a installare la fotocamera scelta.

Se si hanno lavagne di dimensioni superiori a 3,65 m o senza angoli (come le lavagne a parete), è possibile posizionare la fotocamera in qualsiasi punto al centro. Il software di miglioramento seleziona un'area al centro se non riesce a trovare gli angoli della lavagna.

> [!NOTE]
> È possibile usare un nastro di colore scuro o altri elementi per creare un'area della fotocamera del contenuto definita su una lavagna bianca a parete intera.
>
> È possibile scegliere di installare la fotocamera su un treppiede spostabile invece di un supporto permanente. Posizionare il treppiede centrato sulla lavagna. Questa configurazione può essere temporanea o usata in caso di scarse possibilità di sbattere l'attrezzatura. Se si usa un supporto temporaneo, tenere presente che il miglioramento del contenuto avrà un impatto se si sposta la fotocamera dopo la condivisione iniziale e sarà necessario condividerlo di nuovo per correggere il movimento.
>
> Una lavagna da scrittura non bianca non è supportata.

## <a name="supported-cameras"></a>Fotocamere supportate

Per determinare se è possibile usare una fotocamera come videocamera contenuto, vedere Versioni del firmware certificate per le periferiche [audio e video USB.](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals)

In caso contrario, fare riferimento al marketplace Microsoft Teams dispositivi per i kit di fotocamera contenuto supportati [all'indirizzo aka.ms/teamsdevices](https://aka.ms/teamsdevices).

## <a name="camera-settings"></a>Impostazioni fotocamera

Dopo aver installato la fotocamera nella sala, configurarla nella console di Microsoft Teams Rooms chat room:

1. Selezionare **Impostazioni** ![ Impostazioni icona. Accedere come amministratore e selezionare ](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) Dispositivo **Impostazioni**.
2. Nella sezione **Impostazioni predefinite fotocamera** selezionare la fotocamera  del contenuto e verificare che sia selezionata l'opzione Miglioramenti al contenuto.
3. (Facoltativo) Se la fotocamera è stata installata capovolta perché è stata montata dal soffitto, selezionare l'opzione Ruota fotocamera contenuto **di 180°.**
4. Selezionare **Salva e esci.**

![Configurazione della fotocamera del contenuto.](../media/content-camera.png)

È anche possibile modificare queste impostazioni in remoto usando un [file di configurazione XML.](xml-config-file.md)

## <a name="see-also"></a>Vedere anche

[Gestire le impostazioni Microsoft Teams Rooms console in remoto con un file di configurazione XML](xml-config-file.md)

[Requisiti per Microsoft Teams Rooms](requirements.md)


