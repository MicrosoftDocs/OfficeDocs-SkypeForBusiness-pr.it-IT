---
title: Configurare Video Interop Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Riepilogo: configurare il ruolo ViS (Video Interop Server) in Skype for Business Server.'
ms.openlocfilehash: 4148cf404fba4718f56c3c8db7ffe180881b3ae7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835814"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Configurare Video Interop Server in Skype for Business Server
 
**Riepilogo:** Configurare il ruolo Video Interop Server (VIS) in Skype for Business Server.
  
 Configurare le impostazioni che il VIS associerà ai trunk video usando Windows PowerShell. Una configurazione trunk video con ambito globale viene creata dopo l'installazione del servizio VIS. Questa configurazione trunk video viene applicata dal VIS a tutti i trunk che non dispongono di una configurazione trunk video con un ambito più specifico. Si noti che la configurazione del trunk video è una raccolta di impostazioni applicabili ai trunk video.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Configurare trunk video e dial plan

Utilizzare i seguenti comandi Windows PowerShell per specificare la configurazione del trunk video e il dial plan da associare ai nuovi trunk definiti nel Documento di topologia tra il VIS e tutti i gateway video. Tutte queste impostazioni possono essere impostate a livello globale, sito o servizio (gateway video). 
  
Viene creato un dial plan con ambito globale per Skype for Business Server distribuzione. Questo dial plan viene applicato da VIS a tutti i trunk che non dispongono di dial plan con ambito più specifico. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Configurare il sistema VIS utilizzando Windows PowerShell

1. Creare una nuova configurazione trunk video (una raccolta di impostazioni) da utilizzare nel trunk tra VIS e Cisco Unified Communications Manager (CallManager o CUCM), utilizzando il cmdlet Windows PowerShell seguente:
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Se è necessario modificare un trunk video esistente, utilizzare il cmdlet Windows PowerShell seguente:
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Per visualizzare le impostazioni associate a una particolare configurazione trunk video, utilizzare il cmdlet Windows PowerShell seguente:
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Per rimuovere una particolare configurazione trunk video, utilizzare il cmdlet Windows PowerShell seguente (si noti che la configurazione trunk video con ambito globale verrà applicata se non esiste una configurazione trunk video con ambito più specifico per un determinato trunk):
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Stabilire un dial plan da associare al trunk, utilizzando i cmdlet Windows PowerShell seguenti:
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

Il **comando Remove-CsVoiceNormalizationRule** è necessario per ignorare una regola predefinita che interferirà con l'interazione VIS e CUCM prevista.
> [!NOTE]
> [Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) può essere utilizzato per rimuovere un dial plan.
  
Per una chiamata trunk SIP video da un gateway video il cui URI di richiesta contiene un numero non E.164, VIS leggerà il nome del dial plan associato al trunk associato e includerà il nome del dial plan nella parte del contesto telefonico dell'URI richiesta nell'invito inviato da VIS al Front End. L'applicazione di traduzione nel Front End estrae e applica le regole di normalizzazione associate al dial plan all'URI della richiesta.
## <a name="trunk-configuration-options"></a>Opzioni di configurazione trunk

I Windows PowerShell per la configurazione del trunk video menzionati in precedenza erano nuovi Skype for Business Server 2015. Le impostazioni associate alla configurazione del trunk video richiedono una breve spiegazione.
  
 **GatewaySendsRtcpForActiveCalls** Questo parametro determina se i pacchetti RTCP vengono inviati dal VTC al VIS per le chiamate attive. Una chiamata attiva in questo contesto è una chiamata in cui il flusso dei supporti è consentito almeno in una direzione. Se GatewaySendsRtcpForActiveCalls è impostato su True, VIS può terminare una chiamata se non riceve pacchetti RTCP per un periodo superiore a 30 secondi. L'impostazione predefinita è **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Questo parametro determina se i pacchetti RTCP continuano a essere inviati attraverso il trunk per le chiamate che sono state poste in attesa e non si prevede che i pacchetti multimediali scorrono in entrambe le direzioni. VIS può terminare la chiamata, se non ci sono pacchetti RTCP che fluino dal VTC al VIS mentre la chiamata è in attesa. L'impostazione predefinita è **True**. Quando il protocollo SIPTransport è impostato su TCP, questa impostazione viene ignorata.
  
 **EnableMediaEncryptionForSipOverTls** Questo parametro abilita o disabilita SRTP per i supporti quando il protocollo SIPTransport è impostato su TLS. L'impostazione predefinita è **True**. Quando il protocollo SIPTransport è impostato su TCP, questa impostazione viene ignorata.
  
 **EnableSessionTimer** Questo parametro abilita o disabilita i timer di sessione sul lato VIS per ogni finestra di dialogo SIP associata al trunk SIP video. Il valore predefinito è **False**.
  
 **ForwardErrorCorrectionType** Questo parametro viene utilizzato per determinare se la correzione degli errori di inoltro (FEC, Forward Error Correction) per i flussi video deve essere applicata sulla parte tra Video Interop Server e un gateway video. L'impostazione di ForwardErrorCorrectionType su "None" disattiva FEC tra VIS e Video Gateway/VTC. L'impostazione di ForwardErrorCorrectionType su "Cisco" abilita FEC compatibile con i gateway video di Cisco, ad esempio Cisco Unified Communications Manager (CUCM). Il valore predefinito **è None.**
  
## <a name="see-also"></a>Vedere anche

[Configurare CUCM per l'interoperabilità con Skype for Business Server](configure-cucm-for-interoperation.md)