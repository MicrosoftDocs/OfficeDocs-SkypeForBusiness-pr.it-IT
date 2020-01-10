---
title: Distribuire il bypass multimediale in Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Leggere questo argomento per informazioni sui passaggi per distribuire il bypass multimediale con Cloud Connector Edition versione 2,0 e versioni successive.
ms.openlocfilehash: 63d8f9e289c38a50444bee2667c98543e09b875d
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003486"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Distribuire il bypass multimediale in Cloud Connector Edition
 
Leggere questo argomento per informazioni sui passaggi per distribuire il bypass multimediale con Cloud Connector Edition versione 2,0 e versioni successive. 
  
Il bypass multimediale consente a un client di inviare elementi multimediali direttamente alla rete PSTN (Public Switched Telephone Network) Next Hop, ovvero un gateway o un border controller (SBC), ed eliminare il componente cloud Connector Edition dal percorso multimediale. Vedere anche [piano per il bypass multimediale in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Abilitare il bypass multimediale

Per abilitare il bypass multimediale, è necessario configurare il nome DNS del servizio Web di bypass multimediale e attivare il bypass multimediale nella configurazione del tenant. Il servizio Web di bypass multimediale viene distribuito automaticamente in ogni Mediation Server. Un amministratore del tenant deve selezionare un nome per un servizio vocale ibrido (sito) e questo nome deve essere da un dominio SIP registrato per la voce ibrida. Il nome del servizio deve essere lo stesso in tutti gli elettrodomestici di Cloud Connector e in tutti i siti PSTN indipendentemente dalla posizione del client. Il servizio Web dovrebbe essere disponibile solo internamente alla rete.
  
Un amministratore del tenant deve configurare un record DNS nell'Active Directory di produzione interna. Se si dispone di un ambiente multisito complesso, vedere l'esempio seguente [: record DNS del sito Web di bypass multimediale in ambienti multisito complessi](deploy-media-bypass-in-cloud-connector.md#Example). Il record DNS deve essere risolto solo per i client di rete interni. non deve essere risolto per i client di rete esterni.
  
Dopo aver configurato il DNS, connettersi a Skype for business online usando Remote PowerShell con le credenziali di amministratore di Skype for business. Per altre informazioni, vedere [configurare il computer per Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .
  
Nella sessione di PowerShell Immetti i comandi seguenti per abilitare il bypass multimediale:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

L'abilitazione del bypass multimediale è un processo in due passaggi. Il cmdlet New-CsNetworkMedia non salva immediatamente la nuova configurazione. Crea solo le impostazioni in memoria. L'oggetto creato da questo cmdlet deve essere salvato in una variabile e quindi assegnato alla proprietà MediaBypassSettings della configurazione di rete. Per altre informazioni, vedere [esempio: record DNS del sito Web di bypass multimediale in ambienti multisito complessi](deploy-media-bypass-in-cloud-connector.md#Example).
  
La replica tra i componenti locali e online può richiedere fino a 24 ore, quindi Microsoft consiglia di eseguire i comandi necessari prima di abilitare gli utenti.
  
## <a name="confirm-media-bypass-settings"></a>Confermare le impostazioni di bypass multimediale

È possibile controllare le impostazioni di bypass multimediale nel modo seguente. 
  
Per controllare la replica online nel pool di tenant, eseguire il comando seguente in PowerShell remoto:
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Per verificare la replica locale, connettersi a Cloud Connector Mediation Servers, eseguire il comando seguente in PowerShell e verificare che Enabled = true e AlwaysBypass = true
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

Per controllare le impostazioni del client, disconnettersi dal client Skype for business, accedere di nuovo e verificare che il client abbia ricevuto l'URL del servizio nel modo seguente:
  
1. Aprire%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 
    
2. Cercare hybridconfigserviceinternalurl e verificare che l'URL corrisponda a quello definito.
    
## <a name="change-media-bypass-parameters"></a>Modificare i parametri di bypass multimediale

Gli amministratori del tenant possono modificare il nome DNS del servizio Web eseguendo il cmdlet seguente:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> I client devono disconnettersi ed eseguire l'accesso per ottenere il nome del nuovo servizio e riconoscere la modifica. 
  
## <a name="temporarily-disable-media-bypass"></a>Disabilitare temporaneamente il bypass multimediale

Questo scenario potrebbe essere utile per la risoluzione dei problemi o la manutenzione. Per disabilitare il servizio, eseguire i cmdlet seguenti:
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Dopo aver apportato la modifica, potrebbe essere necessario un po' di tempo prima che le modifiche vengano replicate in tutti i connettori cloud. Per verificare lo stato della replica, eseguire il cmdlet seguente in PowerShell in server di mediazione Cloud Connector: 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

Dopo la replica delle modifiche, il servizio Web su Mediation Server inizierà a rifiutare le richieste client per il servizio di bypass multimediale.
  
## <a name="disable-media-bypass-permanently"></a>Disabilitare il bypass multimediale in modo permanente

Per disabilitare definitivamente il bypass multimediale, è necessario che un amministratore del tenant esegua i comandi seguenti: 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Un amministratore dovrà inoltre rimuovere gli indirizzi Web per il bypass multimediale dai server DNS interni. Dopo aver apportato la modifica, potrebbe essere necessario un po' di tempo per modificare la replica in tutti gli elettrodomestici di Cloud Connector. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Esempio: record DNS del sito Web di bypass multimediale in ambienti multisito complessi
<a name="Example"> </a>

I client riceveranno l'indirizzo Web del servizio Web di bypass multimediale da un server DNS interno. Il nome del servizio Web sarà lo stesso in tutti i siti PSTN di appliance Connector e Cloud Connector. In un ambiente multisito complesso è consigliabile usare il criterio DNS di Windows 2016 per la gestione del traffico basato su Geo-location, in modo che i client possano essere reindirizzati al servizio Web locale per la rete. 
  
Per altre informazioni sui criteri DNS di Windows 2016, vedere [usare i criteri DNS per la gestione del traffico basato su Geo-location con i server primari](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).
  
Di seguito è riportato un esempio di configurazione per una società con diversi siti che usano i criteri DNS di Windows 2016 per la gestione del traffico basata su Geo-location.
  
Il nome del servizio di bypass è "hybridvoice.adatum.biz".
  
Il sito di Amsterdam include quattro appliance di connettori cloud distribuiti con gli indirizzi IP di Mediation Server seguenti:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
Il sito di Seattle include tre appliance di connettori cloud distribuiti con gli indirizzi IP di Mediation Server seguenti:
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
Usando la gestione del traffico basato su Geo-location, i server DNS verrebbero configurati come segue:
  
1. Creare subnet client DNS per le subnet di Amsterdam e Seattle.
    
2. Creare ambiti di zona DNS per adatum.biz sia per Amsterdam che per Seattle.
    
3. Creare record DNS in ogni ambito di area DNS.
    
    Amsterdam
    
   - Digitare A;
    
   - Nome: HybridVoice nella zona DNS di adatum.biz
    
   - Destinazione: 192.168.1.45
    
     Creare record aggiuntivi per altri Mediation Server
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Seattle
    
   - Digitare un
    
   - Nome: HybridVoice nella zona DNS di adatum.biz
    
   - Destinazione: 10.10.1.8
    
     Creare record aggiuntivi per altri Mediation Server
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. Creare i criteri DNS che collegano le subnet client agli ambiti di zona appropriati per garantire la risoluzione DNS desiderata.
    
A questo punto, i client che eseguono query DNS dalla subnet di Amsterdam per hybridvoice.adatum.biz restituiranno gli indirizzi 192.168.1.45, 192.168.1.46, 192.168.1.47 e 192.168.1.48, mentre i client che eseguono lo stesso modulo di query Seattle restituiranno 10.10.1.8. 10.10.1.9 e 10.10.1.10.

> [!NOTE]
> Se l'accessorio CCE non sembra ricevere le impostazioni aggiornate, verificare se l'appliance è in grado di contattare il tenant tramite una versione remota di PowerShell. Puoi usare PowerShell remoto per controllare lo stato dell'appliance con Get-CsHybridPSTNAppliance oppure usare PowerShell nell'host CCE per verificare lo stato con Get-CcApplianceStatus.

  
## <a name="see-also"></a>Vedere anche
<a name="Example"> </a>

[Pianificare il bypass multimediale in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)
