---
title: Configurare il server di interoperabilità video in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Riepilogo: configurare il ruolo video Interop Server (VIS) in Skype for Business Server.'
ms.openlocfilehash: 84ab821249ae388bc1ba0dc41cb980c90d4f0853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820696"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Configurare il server di interoperabilità video in Skype for Business Server
 
**Riepilogo:** Configurare il ruolo video Interop Server (VIS) in Skype for Business Server.
  
 Configurare le impostazioni che il VIS associerà ai trunk video utilizzando Windows PowerShell. Viene creata una configurazione trunk video con ambito globale dopo l'installazione del servizio VIS. Questa configurazione del trunk video viene applicata dal VIS a tutti i trunk che non dispongono di una configurazione trunk video con un ambito più specifico. Si noti che la configurazione trunk video è una raccolta di impostazioni applicabile ai trunk video.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Configurare trunk video e dial plan

Utilizzare i seguenti comandi di Windows PowerShell per specificare la configurazione e il dial plan del trunk video da associare ai trunk appena definiti definiti nel documento della topologia tra il VIS e tutti i gateway video. Tutte queste impostazioni possono essere impostate nei livelli Global, site o Service (video gateway). 
  
Viene creato un dial plan con ambito globale per la distribuzione di Skype for Business Server. Questo dial plan viene applicato da VIS a tutti i trunk che non dispongono di un dial plan con un ambito più specifico. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Configurare il VIS tramite Windows PowerShell

1. Creare una nuova configurazione trunk video (una raccolta di impostazioni) da utilizzare nel trunk tra il VIS e Cisco Unified Communications Manager (CallManager o un CUCM), utilizzando il seguente cmdlet di Windows PowerShell:
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Se è presente un trunk video esistente che deve essere modificato, utilizzare il seguente cmdlet di Windows PowerShell:
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Per visualizzare le impostazioni associate a una determinata configurazione del trunk video, utilizzare il seguente cmdlet di Windows PowerShell:
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Per rimuovere una determinata configurazione del trunk video, utilizzare il seguente cmdlet di Windows PowerShell (si noti che la configurazione del trunk video con ambito globale verrà applicata se non è disponibile una configurazione trunk video più specifica per un trunk specifico):
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Stabilire un dial plan da associare al trunk, utilizzando i cmdlet di Windows PowerShell seguenti:
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

Il comando **Remove-CsVoiceNormalizationRule** è necessario per eseguire l'override di una regola predefinita che interferirà con l'interazione vis e un CUCM prevista.
> [!NOTE]
> [Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) può essere utilizzato per rimuovere un dial plan.
  
Per una chiamata trunk SIP video da un gateway video il cui URI di richiesta contiene un numero non E. 164, VIS leggerà il nome del dial plan associato al trunk associato e includerà il nome del dial plan nella parte relativa al contesto telefonico dell'URI della richiesta nell'invito che VIS invia al front end. L'applicazione di conversione sul front-end estrae e applica le regole di normalizzazione associate al dial plan all'URI della richiesta.
## <a name="trunk-configuration-options"></a>Opzioni di configurazione trunk

I cmdlet di Windows PowerShell per la configurazione del trunk video menzionati in precedenza erano nuovi di Skype for Business Server 2015. Le impostazioni associate alla configurazione del trunk video richiedono una breve spiegazione.
  
 **GatewaySendsRtcpForActiveCalls** Questo parametro determina se i pacchetti di RTCP vengono inviati da videoconferenza al VIS per le chiamate attive. Una chiamata attiva in questo contesto è una chiamata in cui il flusso dei supporti è consentito almeno in una direzione. Se GatewaySendsRtcpForActiveCalls è impostato su true, VIS può terminare una chiamata se non riceve i pacchetti RTCP per un periodo superiore a 30 secondi. L'impostazione predefinita è **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Questo parametro determina se i pacchetti di RTCP continuano a essere inviati attraverso il trunk per le chiamate che sono state messe in attesa e non si prevede che il flusso di pacchetti multimediali sia in entrambe le direzioni. VIS può terminare la chiamata, se non ci sono pacchetti di RTCP che scorrono da videoconferenza a VIS mentre la chiamata è in attesa. L'impostazione predefinita è **True**. Quando il protocollo SIPTransport è impostato su TCP, questa impostazione viene ignorata.
  
 **EnableMediaEncryptionForSipOverTls** Questo parametro consente di abilitare o disabilitare SRTP per il contenuto multimediale quando il protocollo SIPTransport è impostato su TLS. L'impostazione predefinita è **True**. Quando il protocollo SIPTransport è impostato su TCP, questa impostazione viene ignorata.
  
 **EnableSessionTimer** Questo parametro consente di abilitare o disabilitare i timer di sessione sul fianco VIS per ogni finestra di dialogo SIP associata al trunk SIP video. Il valore predefinito è **False**.
  
 **ForwardErrorCorrectionType** Questo parametro viene utilizzato per determinare se la correzione degli errori di inoltro (FEC) per i flussi video deve essere applicata sulla gamba tra il video Interop server e un gateway video. L'impostazione di ForwardErrorCorrectionType su "None" Disattiva FEC tra VIS e video gateway/videoconferenza. L'impostazione di ForwardErrorCorrectionType su "Cisco" Abilita FEC compatibile con i gateway video da Cisco, come Cisco Unified Communications Manager (un CUCM). Il valore predefinito è **None**.
  
## <a name="see-also"></a>Vedere anche

[Configurare un CUCM per l'interoperabilità con Skype for Business Server](configure-cucm-for-interoperation.md)
