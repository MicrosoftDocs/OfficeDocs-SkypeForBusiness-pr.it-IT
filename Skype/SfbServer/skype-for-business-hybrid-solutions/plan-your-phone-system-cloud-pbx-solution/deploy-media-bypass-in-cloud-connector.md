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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Leggere questo argomento per informazioni sui passaggi per la distribuzione di bypass multimediale con Cloud Connector Edition versione 2,0 e versioni successive.
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359312"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Distribuire il bypass multimediale in Cloud Connector Edition
 
> [!Important]
> Cloud Connector Edition si ritirerà il 31 luglio 2021 insieme a Skype for business online. Dopo che l'organizzazione ha eseguito l'aggiornamento ai team, informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Leggere questo argomento per informazioni sui passaggi per la distribuzione di bypass multimediale con Cloud Connector Edition versione 2,0 e versioni successive. 
  
Il bypass multimediale consente a un client di inviare contenuti multimediali direttamente alla rete PSTN (Public Switched Telephone Network), ovvero a un gateway o a un session border controller (SBC), ed eliminare il componente cloud Connector Edition dal percorso multimediale. Vedere anche [Plan for Media Bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Abilita bypass multimediale

Per abilitare il bypass multimediale, è necessario configurare il nome DNS del servizio Web bypass multimediale e attivare il bypass multimediale nella configurazione tenant. Il servizio Web bypass multimediale viene distribuito automaticamente su ogni Mediation Server. Un amministratore tenant deve scegliere un nome per un servizio vocale ibrido (sito) e questo nome deve provenire da un dominio SIP registrato per la voce ibrida. Il nome del servizio deve essere lo stesso in tutti gli apparecchi del connettore Cloud e in tutti i siti PSTN indipendentemente dalla posizione del client. Il servizio Web deve essere disponibile solo all'interno della rete.
  
Un amministratore tenant deve configurare un record a DNS nell'Active Directory di produzione interna. Se si dispone di un ambiente multi-sito complesso, vedere l'esempio seguente [: record DNS dei siti Web di bypass multimediale in ambienti multisito complessi](deploy-media-bypass-in-cloud-connector.md#Example). Il record DNS deve essere risolto solo per i client di rete interni. non deve essere risolto per i client di rete esterni.
  
Dopo aver configurato DNS, connettersi a Skype for business online tramite Remote PowerShell con le credenziali di amministratore di Skype for business. Per ulteriori informazioni, vedere [configurare il computer per Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .
  
Nella sessione di PowerShell, immettere i seguenti comandi per abilitare il bypass multimediale:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

L'abilitazione del bypass multimediale è un processo in due passaggi. Il cmdlet New-CsNetworkMedia non salva immediatamente la nuova configurazione. consente di creare solo le impostazioni in memoria. L'oggetto creato da questo cmdlet deve essere salvato in una variabile e quindi assegnato alla proprietà MediaBypassSettings della configurazione di rete. Per ulteriori informazioni, vedere [esempio: record DNS dei siti Web di bypass multimediale in ambienti multisito complessi](deploy-media-bypass-in-cloud-connector.md#Example).
  
La replica tra i componenti locali e online può richiedere fino a 24 ore, pertanto Microsoft consiglia di eseguire i comandi necessari prima di abilitare gli utenti.
  
## <a name="confirm-media-bypass-settings"></a>Confermare le impostazioni di bypass multimediale

È possibile controllare le impostazioni di bypass multimediale come indicato di seguito. 
  
Per controllare la replica online nel pool tenant, eseguire il comando riportato di seguito in Remote PowerShell:
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Per verificare la replica locale, connettersi al Cloud Connector Mediation Server, eseguire il comando seguente in PowerShell e verificare che Enabled = true e AlwaysBypass = true
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

Per controllare le impostazioni del client, disconnettersi dal client Skype for business, eseguire l'accesso e verificare che il client abbia ricevuto l'URL del servizio, come indicato di seguito:
  
1. Aprire%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 
    
2. Cercare hybridconfigserviceinternalurl e confermare che l'URL corrisponda a quello definito.
    
## <a name="change-media-bypass-parameters"></a>Modificare i parametri di bypass multimediale

Gli amministratori tenant sono in grado di modificare il nome DNS del servizio Web eseguendo il cmdlet seguente:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> I client devono disconnettersi ed eseguire l'accesso per ottenere il nuovo nome del servizio e riconoscere la modifica. 
  
## <a name="temporarily-disable-media-bypass"></a>Disattiva temporaneamente il bypass multimediale

Questo scenario potrebbe essere utile per la risoluzione dei problemi o la manutenzione. Per disabilitare il servizio, eseguire i cmdlet seguenti:
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Dopo aver apportato la modifica, potrebbe essere necessario un po' di tempo prima che le modifiche vengano replicate in tutti i connettori cloud. Per controllare lo stato della replica, eseguire il seguente cmdlet in PowerShell su cloud Connector Mediation Server: 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

Dopo la replica delle modifiche, il servizio Web sul Mediation Server inizierà a rifiutare le richieste client per il servizio di bypass multimediale.
  
## <a name="disable-media-bypass-permanently"></a>Disabilitare il bypass multimediale in modo permanente

Per disabilitare definitivamente il bypass multimediale, è necessario che un amministratore tenant esegua i comandi seguenti: 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Anche un amministratore dovrà rimuovere gli indirizzi Web per il bypass multimediale dai server DNS interni. Dopo aver apportato la modifica, potrebbe essere necessario un po' di tempo prima che le modifiche vengano replicate in tutti gli apparecchi del connettore Cloud. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Esempio: record DNS dei siti Web di bypass multimediale in ambienti multisito complessi
<a name="Example"> </a>

I client riceveranno l'indirizzo Web del servizio Web bypass multimediale da un server DNS interno. Il nome del servizio Web sarà lo stesso in tutti i siti PSTN dei connettori cloud e del connettore Cloud. In un ambiente multisito complesso, è consigliabile utilizzare il criterio DNS di Windows 2016 per la gestione del traffico basato sulla posizione geografica, in modo che i client possano essere reindirizzati al servizio Web locale per la rete. 
  
Per ulteriori informazioni sui criteri DNS di Windows 2016, vedere [Use DNS Policy for Geo-location based Traffic Management with primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).
  
Di seguito è riportato un esempio di configurazione per una società con diversi siti che utilizzano i criteri DNS di Windows 2016 per la gestione del traffico basato sulla posizione geografica.
  
Il nome del servizio di bypass è' hybridvoice.adatum.biz '.
  
Il sito di Amsterdam ha quattro appliance di connettori cloud distribuiti con gli indirizzi IP di Mediation Server seguenti:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
Il sito di Seattle dispone di tre appliance di connettori cloud distribuiti con gli indirizzi IP di Mediation Server seguenti:
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
Utilizzando la gestione del traffico basato sulla posizione geografica, i server DNS verrebbero configurati nel modo seguente:
  
1. Creare subnet client DNS per le subnet di Amsterdam e Seattle.
    
2. Creare gli ambiti delle aree DNS per adatum.biz sia per Amsterdam che per Seattle.
    
3. Creare record DNS in ogni ambito della zona DNS.
    
    Amsterdam
    
   - Digitare A;
    
   - Nome: HybridVoice nella zona DNS di adatum.biz
    
   - Destinazione: 192.168.1.45
    
     Creare record aggiuntivi per altri Mediation Server
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Seattle
    
   - Digitare A
    
   - Nome: HybridVoice in adatum.biz DNS zone
    
   - Destinazione: 10.10.1.8
    
     Creare record aggiuntivi per altri Mediation Server
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. Creare il criterio DNS che connette le subnet client agli ambiti di area corretti per garantire la risoluzione DNS desiderata.
    
A questo punto, i client che eseguono query DNS dalla subnet di Amsterdam per hybridvoice.adatum.biz restituiranno gli indirizzi 192.168.1.45, 192.168.1.46, 192.168.1.47 e 192.168.1.48, mentre i client che eseguono lo stesso modulo di query Seattle restituiranno 10.10.1.8, 10.10.1.9 e 10.10.1.10.

> [!NOTE]
> Se l'apparecchio CCE non sembra ricevere le impostazioni aggiornate, controllare se l'apparecchio è in grado di contattare il tenant tramite Remote PowerShell. È possibile utilizzare Remote PowerShell per controllare lo stato dell'accessorio con Get-CsHybridPSTNAppliance oppure utilizzare PowerShell nell'host CCE per controllare lo stato con Get-CcApplianceStatus.

  
## <a name="see-also"></a>Vedere anche
<a name="Example"> </a>

[Pianificare il bypass multimediale in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)
