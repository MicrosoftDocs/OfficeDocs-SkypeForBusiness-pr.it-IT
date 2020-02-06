---
title: Risoluzioni video client Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 'Riepilogo: rivedere i requisiti del client video durante la pianificazione per Skype for Business Server.'
ms.openlocfilehash: f51e9369cfba636ae37205a6e56e27c7622f12e6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803496"
---
# <a name="skype-for-business-client-video-resolutions"></a>Risoluzioni video client Skype for business
 
**Riepilogo:** Esaminare i requisiti del video client durante la pianificazione per Skype for Business Server.
  
Questo articolo descrive il supporto hardware video per le videochiamate Skype for business e descrive come determinare la qualità video prevista per varie configurazioni di computer, tablet e dispositivi mobili. 
  
I professionisti IT troveranno queste informazioni utili per valutare l'idoneità dei portatili già in uso nella propria organizzazione o in considerazione per l'uso. Possono inoltre eseguire ricerche nel [Catalogo soluzioni](https://partnersolutions.skypeforbusiness.com/solutionscatalog) per informazioni su dispositivi specifici.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Requisiti e funzionalità di Windows desktop, Mac e tablet video

Skype for business usa l'accelerazione hardware per la codifica e la decodifica video in base allo standard di codifica video avanzato H. 264/MPEG-4 Part 10. In questo modo i computer con velocità di clock della CPU più bassa permettono di codificare e decodificare video con risoluzione superiore. I requisiti hardware video variano in base alla configurazione del computer e alla risoluzione video desiderata.
  
Vedi anche [requisiti hardware per Windows e Mac](https://products.office.com/en-us/office-system-requirements).
  
### <a name="video-hardware-requirements"></a>Requisiti hardware video

|**Funzionalità**|**Requisito**|
|:-----|:-----|
|Decodifica H. 264 con accelerazione hardware con DirectX Video Acceleration (DXVA)  <br/> |• La scheda grafica deve supportare DirectX 9,0 e deve esporre la modalità di decodifica DXVA2_ModeH264_VLD_NoFGT e l'API DirectX 9.  <br/> • È necessario installare il driver della scheda grafica più recente.  <br/> |
|Codifica H. 264 con accelerazione hardware: requisiti del chipset  <br/> |Sono supportate le soluzioni di codifica video con accelerazione hardware Intel seguenti:  <br/> • I chipset Intel HD Graphics 2000, 2500, 3000 e 4000 di seconda e terza generazione (o versioni successive) con codificatori video hardware integrati. È necessario installare il driver di grafica Intel HD 15.28.9.2884 o il driver più recente che contiene le opzioni seguenti:  <br/> • Visualizzare il driver 9.17.10.2884 o il driver più recente  <br/> • Hardware Media Foundation Transform (HMFT) versione 3.12.10.31 o l'ultima HMFT  <br/> Sono supportate le seguenti soluzioni di codifica video con accelerazione hardware AMD:  <br/> • Motore di codec AMD video, disponibile in diverse schede grafiche discrete e in unità di elaborazione accelerate integrate dei processori accelerati della serie AMD A. Il driver del motore di codec AMD video 9.12.0.0 o versione successiva deve essere installato.  <br/> |
|Codifica H. 264 con accelerazione hardware: requisiti della fotocamera  <br/> |Videocamere USB con codificatore hardware H. 264 integrato conforme alla specifica UVC (USB video Class) versione 1,5.  <br/> **Nota:** Skype for business supporta le telecamere UVC 1,5 con Windows 8 o Windows 8,1, che include il supporto per UVC 1,5. Dato che Windows 7 non include il supporto per UVC 1,5, Skype for business tratta le fotocamere UVC 1,5 come normali fotocamere senza supporto per la codifica hardware. <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Determinazione delle funzionalità di codifica e decodifica video H. 264

In genere, esistono quattro fattori principali che determinano la funzionalità di codifica e decodifica massima di una particolare configurazione del computer:
  
- Supporto della decodifica con accelerazione hardware tramite DXVA
    
- Supporto per la codifica accelerata hardware
    
- Numero di core fisici
    
- Indice di Windows Experience (WEI)
    
Lo strumento di valutazione di sistema Windows (WinSAT) determina il WEI. Quando si esegue lo strumento WinSAT, viene generato un documento XML formale. Assessment nel computer della directory%windir%\Performance\WinSAT\DataStore. Questo file XML contiene i due punteggi seguenti che rivestono particolare importanza per la determinazione delle funzionalità di codifica e decodifica:
  
- VideoEncodeScore indica la funzionalità di codifica video basata sul software del computer.
    
- Il valore GraphicsScore indica la funzionalità di codifica accelerata hardware del computer.
    
Le tre tabelle seguenti spiegano la funzionalità di codifica e decodifica massima per diversi tipi di PC, a seconda dell'accelerazione hardware supportata. Per le risoluzioni di 640x360 e successive, la frequenza dei fotogrammi supportata massima è di 30 fotogrammi al secondo (fps). Per le risoluzioni inferiori a 640x360, la frequenza dei fotogrammi massima supportata è di 15 fps.
  
**Computer senza DXVA e senza codificatore accelerato hardware**

|**Risoluzione encoder in grado**|**Risoluzione del decoder in grado**|**Requisito**|
|:-----|:-----|:-----|
|424x240  <br/> |424x240 (640x360 a 15fps per gli scenari di ricezione solo)  <br/> |1 core e VideoEncodeScore ≥ 4,0  <br/> |
|640x360  <br/> |640x360  <br/> |2 core e VideoEncodeScore ≥ 4,5  <br/> |
|640x360  <br/> |1280x720  <br/> |2 core e VideoEncodeScore ≥ 4,5  <br/> |
|640x360  <br/> |1920x1080  <br/> |4 core e VideoEncodeScore ≥ 4,5  <br/> |
|1280x720  <br/> |1280x720  <br/> |4 core e VideoEncodeScore ≥ 7,3  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 core e VideoEncodeScore ≥ 7,3  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |N/D  <br/> |
   
**Computer con DXVA ma senza codificatore accelerato hardware**

|**Risoluzione encoder in grado**|**Risoluzione del decoder in grado**|**Requisito**|
|:-----|:-----|:-----|
|424x240  <br/> |1920x1080  <br/> |1 core e VideoEncodeScore ≥ 3,0  <br/> |
|640x360  <br/> |1920x1080  <br/> |2 core e VideoEncodeScore ≥ 4,5  <br/> |
|960x540  <br/> |1920x1080  <br/> |2 core e VideoEncodeScore ≥ 6,0  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 core e VideoEncodeScore ≥ 6,7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4 core e VideoEncodeScore ≥ 8,2  <br/> |
   
> [!NOTE]
> Il Punteggio WinSAT in Windows 7 è limitato a un massimo di 7,9. Di conseguenza, la funzionalità di codifica per un computer senza un codificatore accelerato hardware può essere raggiunta solo in Windows 8 o Windows 8,1, dove il punteggio massimo di WinSAT è 9,9. 
  
**Computer con DXVA e con encoder accelerato hardware per grafica Intel HD**

|**Risoluzione encoder in grado**|**Risoluzione del decoder in grado**|**Requisito**|
|:-----|:-----|:-----|
|1280x720  <br/> |1920x1080  <br/> |Tutte le seconde e terze generazioni di Intel HD Graphics  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |2 ° e 3 ° generazione di grafica Intel HD e GraphicsScore ≥ 5,0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Funzionalità video per dispositivi mobili

La tabella seguente descrive le risoluzioni video massime disponibili nei dispositivi mobili supportati. Per altre informazioni sul supporto di dispositivi mobili, [confronto tra funzionalità client per dispositivi mobili per Skype for business](mobile-feature-comparison.md).
  
|**Funzionalità**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Risoluzione massima della codifica H. 264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S e versioni successive  <br/> |VGA: iPad 2 e versioni successive/iPad mini 1 e versioni successive  <br/> 720p: iPad Air/iPad mini 2/iPad Pro e versioni successive  <br/> |Fino a VGA a seconda del modello di dispositivo  <br/> |
|Risoluzione massima di decodifica H. 264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S e versioni successive  <br/> |VGA: iPad 2 e versioni successive/iPad mini 1 e versioni successive  <br/> 720p: iPad Air/iPad mini 2/iPad Pro e versioni successive  <br/> |Fino a VGA a seconda del modello di dispositivo  <br/> |
   

