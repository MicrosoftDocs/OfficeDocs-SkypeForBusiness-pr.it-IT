---
title: Configurare il server di interoperabilità video in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Riepilogo: configurare il ruolo di video Interop Server (VIS) in Skype for Business Server.'
ms.openlocfilehash: 3c0b211897afdde0fc0a01e255cdc14bc466f65c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195403"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Configurare il server di interoperabilità video in Skype for Business Server
 
**Riepilogo:** Configurare il ruolo di video Interop Server (VIS) in Skype for Business Server.
  
 Configurare le impostazioni che il VIS associerà ai trunk video con Windows PowerShell. Viene creata una configurazione trunk video con ambito globale dopo l'installazione del servizio VIS. Questa configurazione del trunk video viene applicata dal VIS a tutti i trunk che non hanno la configurazione del trunk video con un ambito più specifico. Tieni presente che la configurazione trunk video è una raccolta di impostazioni applicabili ai trunk video.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Configurare il trunk e il dial plan video

USA i comandi di Windows PowerShell seguenti per specificare la configurazione del trunk video e il dial plan da associare ai nuovi trunk definiti nel documento di topologia tra il VIS e tutti i gateway video. Tutte queste impostazioni possono essere impostate nei livelli globale, del sito o del servizio (gateway video). 
  
Un dial plan con ambito globale viene creato per la distribuzione di Skype for Business Server. Questo dial plan viene applicato da VIS a tutti i trunk che non hanno un piano di chiamata con un ambito più specifico. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Configurare il VIS con Windows PowerShell

1. Creare una nuova configurazione trunk video (una raccolta di impostazioni) da usare nel trunk tra il VIS e Cisco Unified Communications Manager (CallManager o CUCM) usando il cmdlet di Windows PowerShell seguente:
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Se è presente un trunk video esistente che deve essere modificato, usare il cmdlet di Windows PowerShell seguente:
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Per visualizzare le impostazioni associate a una particolare configurazione del trunk video, usare il cmdlet di Windows PowerShell seguente:
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Per rimuovere una particolare configurazione del trunk video, usare il cmdlet di Windows PowerShell seguente (si noti che la configurazione del trunk video con ambito globale verrà applicata se non esiste una configurazione trunk video più specifica per un trunk specifico):
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Stabilire un dial plan da associare al trunk, usando i cmdlet di Windows PowerShell seguenti:
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

Il comando **Remove-CsVoiceNormalizationRule** è necessario per eseguire l'override di una regola predefinita che interferisce con l'interazione vis e CUCM prevista.
> [!NOTE]
> [Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) può essere usato per rimuovere un dial plan.
  
Per una chiamata trunk SIP video da un gateway video il cui URI di richiesta contiene un numero diverso da E. 164, VIS leggerà il nome del dial plan associato al trunk associato e includerà il nome del dial plan nella parte del contesto telefonico dell'URI della richiesta nell'invito che VI S invia al front-end. L'applicazione di traduzione nel front-end estrae e applica le regole di normalizzazione associate al dial plan all'URI della richiesta.
## <a name="trunk-configuration-options"></a>Opzioni di configurazione trunk

I cmdlet di Windows PowerShell per la configurazione del trunk video menzionati in precedenza erano nuovi per Skype for Business Server 2015. Le impostazioni associate alla configurazione del trunk video richiedono una breve spiegazione.
  
 **GatewaySendsRtcpForActiveCalls** Questo parametro determina se i pacchetti RTCP vengono inviati da VTC al VIS per le chiamate attive. Una chiamata attiva in questo contesto indica una chiamata in cui è consentito il flusso degli elementi multimediali almeno in una direzione. Se GatewaySendsRtcpForActiveCalls è impostato su true, VIS può terminare una chiamata se non riceve pacchetti RTCP per un periodo che supera i 30 secondi. Il valore predefinito è **true**.
  
 **GatewaySendsRtcpForCallsOnHold** Questo parametro determina se i pacchetti di RTCP continuano a essere inviati attraverso il trunk per le chiamate che sono state poste in attesa e che non si prevede che il flusso di pacchetti multimediali sia in entrambe le direzioni. VIS può terminare la chiamata, se non ci sono pacchetti RTCP che scorrono da VTC a VIS mentre la chiamata è in attesa. Il valore predefinito è **true**. Quando il protocollo SIPTransport è impostato su TCP, questa impostazione viene ignorata.
  
 **EnableMediaEncryptionForSipOverTls** Questo parametro Abilita o Disabilita SRTP per elementi multimediali quando il protocollo SIPTransport è impostato su TLS. Il valore predefinito è **true**. Quando il protocollo SIPTransport è impostato su TCP, questa impostazione viene ignorata.
  
 **EnableSessionTimer** Questo parametro Abilita o Disabilita i timer di sessione sul lato VIS per ogni finestra di dialogo SIP associata al trunk SIP video. Il valore predefinito è **false**.
  
 **ForwardErrorCorrectionType** Questo parametro viene usato per determinare se la correzione degli errori in avanti (FEC) per i flussi video deve essere applicata alla gamba tra il video Interop server e un gateway video. L'impostazione di ForwardErrorCorrectionType su "None" Disattiva FEC tra VIS e video gateway/VTC. L'impostazione di ForwardErrorCorrectionType su "Cisco" consente la compatibilità con i gateway video per Cisco, ad esempio Cisco Unified Communications Manager (CUCM). Il valore predefinito è **None**.
  
## <a name="see-also"></a>Vedere anche

[Configurare CUCM per l'interoperabilità con Skype for Business Server](configure-cucm-for-interoperation.md)
