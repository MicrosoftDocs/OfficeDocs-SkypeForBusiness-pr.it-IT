---
title: Risoluzioni video del client Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Riepilogo: esaminare i requisiti video del client durante la pianificazione di Skype for Business Server.'
ms.openlocfilehash: 9be23512462781c55ef94b72b4dbbba60e15e5ba
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816056"
---
# <a name="skype-for-business-client-video-resolutions"></a>Risoluzioni video del client Skype for Business
 
**Riepilogo:** Esaminare i requisiti video del client durante la pianificazione di Skype for Business Server.
  
Questo articolo descrive il supporto hardware video per le videochiamate di Skype for Business e descrive come determinare la qualità video prevista per varie configurazioni di computer, tablet e dispositivi mobili. 
  
I professionisti IT troveranno queste informazioni utili per valutare l'idoneità dei portatili già in uso nell'organizzazione o in considerazione per l'utilizzo. Possono inoltre cercare informazioni [su](https://partnersolutions.skypeforbusiness.com/solutionscatalog) dispositivi specifici nel Catalogo soluzioni.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Requisiti e funzionalità video di Windows desktop, Mac e tablet

Skype for Business usa l'accelerazione hardware per la codifica video e la decodifica basata sullo standard H.264/MPEG-4 Parte 10 Advanced Video Coding. Ciò consente ai computer con velocità di clock della CPU inferiori di codificare e decodificare video a risoluzione superiore. I requisiti hardware video variano a seconda della configurazione del computer e alla risoluzione video desiderata.
  
Vedi anche [i requisiti hardware di Windows e Mac.](https://products.office.com/office-system-requirements)
  
### <a name="video-hardware-requirements"></a>Requisiti hardware video

|**Caratteristica**|**Requisito**|
|:-----|:-----|
|Decodifica H.264 con accelerazione hardware mediante DirectX Video Acceleration (DXVA)  <br/> |• La scheda grafica deve supportare DirectX 9.0 ed esporre la modalità DXVA2_ModeH264_VLD_NoFGT decodifica e l'API DirectX 9.  <br/> • È necessario installare il driver della scheda grafica più recente.  <br/> |
|Codifica H.264 con accelerazione hardware: requisiti del chipset  <br/> |Sono supportate le seguenti soluzioni di codifica video con accelerazione hardware Intel:  <br/> • Chipset Intel HD Graphics 2000, 2500, 3000 e 4.000 di seconda e terza generazione (o versioni successive) con codificatori video hardware integrati. È necessaria l'installazione del driver di grafica Intel HD 15.28.9.2884 o del driver più recente contenente quanto segue:  <br/> • Driver video 9.17.10.2884 o il driver più recente  <br/> • Hardware Media Foundation Transform (HMFT) versione 3.12.10.31 o HMFT più recente  <br/> Sono supportate le soluzioni di codifica video con accelerazione hardware AMD seguenti:  <br/> • Motore codec video AMD, disponibile in diverse schede grafiche discrete e in unità di elaborazione accelerate integrate di processori accelerati AMD serie A. Deve essere installato il driver amD Video Codec Engine 9.12.0.0 o versione successiva.  <br/> |
|Codifica H.264 con accelerazione hardware: requisiti fotocamera  <br/> |Fotocamere video USB con codificatore H.264 integrato conforme alla specifica USB Video Class (UVC) versione 1.5.  <br/> **Nota:** Skype for Business supporta fotocamere UVC 1.5 con Windows 8 o Windows 8.1, che include il supporto per UVC 1.5. Poiché Windows 7 non include il supporto per UVC 1.5, Skype for Business considera le fotocamere UVC 1.5 come fotocamere normali senza supporto della codifica hardware. <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Determinazione delle funzionalità di codifica e decodifica video H.264

In generale, esistono quattro fattori principali che determinano la capacità di codifica e decodifica massima di una particolare configurazione di computer:
  
- Supporto per decodifica con accelerazione hardware mediante DXVA
    
- Supporto per la codifica con accelerazione hardware
    
- Numero di core fisici
    
- Indice prestazioni Windows
    
Lo strumento Valutazione sistema Windows (WinSAT) determina l'Indice prestazioni Windows. Quando si esegue lo strumento Valutazione sistema Windows, viene generato un documento XML Formal.Assessment nella directory %windir%\Performance\WinSAT\DataStore del computer. Questo file XML contiene i due punteggi indicati di seguito di particolare importanza per determinare le funzionalità di codifica e decodifica:
  
- VideoEncodeScore indica le capacità di codifica video basata su software del computer.
    
- Il valore GraphicsScore indica la capacità di codifica con accelerazione hardware del computer.
    
Nelle tre tabelle seguenti sono indicate le capacità massime di codifica e decodifica per diversi tipi di PC a seconda dell'accelerazione hardware supportata. Per risoluzioni pari a 640x360 e superiori, la massima frequenza dei fotogrammi supportata è pari a 30 fotogrammi al secondo (fps). Per risoluzioni inferiori a 640x360, la massima velocità dei fotogrammi supportata è pari a 15 fps.
  
**Computer senza DXVA e senza codificatore con accelerazione hardware**

|**Risoluzione codificatore**|**Risoluzione decodificatore**|**Requisito**|
|:-----|:-----|:-----|
|424x240  <br/> |424x240 (640x360 a 15 fps solo per scenari di ricezione)  <br/> |1 core e VideoEncodeScore ≥ 4,0  <br/> |
|640x360  <br/> |640x360  <br/> |2 core e VideoEncodeScore ≥ 4,5  <br/> |
|640x360  <br/> |1280x720  <br/> |2 core e VideoEncodeScore ≥ 4,5  <br/> |
|640x360  <br/> |1920x1080  <br/> |4 core e VideoEncodeScore ≥ 4,5  <br/> |
|1280x720  <br/> |1280x720  <br/> |4 core e VideoEncodeScore ≥ 7,3  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 core e VideoEncodeScore ≥ 7,3  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |N/D  <br/> |
   
**Computer con DXVA ma senza codificatore con accelerazione hardware**

|**Risoluzione codificatore**|**Risoluzione decodificatore**|**Requisito**|
|:-----|:-----|:-----|
|424x240  <br/> |1920x1080  <br/> |1 core e VideoEncodeScore = 3,0  <br/> |
|640x360  <br/> |1920x1080  <br/> |2 core e VideoEncodeScore ≥ 4,5  <br/> |
|960x540  <br/> |1920x1080  <br/> |2 core e VideoEncodeScore ≥ 6,0  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 core e VideoEncodeScore ≥ 6,7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4 core e VideoEncodeScore ≥ 8,2  <br/> |
   
> [!NOTE]
> Il punteggio WinSAT in Windows 7 è limitato a un massimo di 7,9. Pertanto, la funzionalità di codifica per un computer senza codificatore con accelerazione hardware può essere ottenuta solo in Windows 8 o Windows 8.1, dove il punteggio WinSAT massimo è 9,9. 
  
**Computer con DXVA e con codificatore con accelerazione hardware Intel HD Graphics**

|**Risoluzione codificatore**|**Risoluzione decodificatore**|**Requisito**|
|:-----|:-----|:-----|
|1280x720  <br/> |1920x1080  <br/> |Tutti i driver Intel HD Graphics di seconda e terza generazione  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |Driver Intel HD Graphics di seconda e terza generazione e GraphicsScore ≥ 5,0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Funzionalità video per dispositivi mobili

Nella tabella seguente vengono descritte le risoluzioni video massime disponibili nei dispositivi mobili supportati. Per altre informazioni sul supporto dei dispositivi mobili, confronto [delle funzionalità del client mobile per Skype for Business.](mobile-feature-comparison.md)
  
|**Caratteristica**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Risoluzione massima codifica H.264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S e versioni successive  <br/> |VGA: iPad 2 e versioni successive/iPad mini 1 e versioni successive  <br/> 720p: iPad Air/iPad mini 2/iPad Pro e versioni successive  <br/> |Fino a VGA a seconda del modello di dispositivo  <br/> |
|Risoluzione massima decodifica H.264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S e versioni successive  <br/> |VGA: iPad 2 e versioni successive/iPad mini 1 e versioni successive  <br/> 720p: iPad Air/iPad mini 2/iPad Pro e versioni successive  <br/> |Fino a VGA a seconda del modello di dispositivo  <br/> |
   

