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
description: Leggere questo argomento per informazioni sulla procedura per distribuire il bypass multimediale con Cloud Connector Edition versione 2.0 e successive.
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359312"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Distribuire il bypass multimediale in Cloud Connector Edition
 
> [!Important]
> Cloud Connector Edition andrà in ritiro il 31 luglio 2021 insieme a Skype for Business online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Leggere questo argomento per informazioni sulla procedura per distribuire il bypass multimediale con Cloud Connector Edition versione 2.0 e successive. 
  
Il bypass multimediale consente a un client di inviare contenuti multimediali direttamente all'hop successivo PSTN (Public Switched Telephone Network), ovvero un gateway o un Session Border Controller (SBC), ed eliminare il componente Cloud Connector Edition dal percorso multimediale. Vedere anche [Pianificare il bypass multimediale in Cloud Connector Edition.](plan-for-media-bypass-in-cloud-connector-edition.md)
  
## <a name="enable-media-bypass"></a>Abilita bypass multimediale

Per abilitare il bypass multimediale, è necessario configurare il nome DNS del servizio Web di bypass multimediale e attivare il bypass multimediale nella configurazione tenant. Il servizio Web di bypass multimediale viene distribuito automaticamente in ogni Mediation Server. Un amministratore tenant deve selezionare un nome per un servizio vocale ibrido (sito) e questo nome deve derivare da un dominio SIP registrato per la voce ibrida. Il nome del servizio deve essere lo stesso in tutti i dispositivi Cloud Connector e in tutti i siti PSTN indipendentemente dalla posizione del client. Il servizio Web deve essere disponibile solo internamente nella rete.
  
Un amministratore tenant deve configurare un record A DNS in Active Directory di produzione interna. Se si dispone di un ambiente multisnode complesso, vedere l'esempio in Esempio: record DNS del sito Web bypass multimediale [in ambienti multisodei complessi.](deploy-media-bypass-in-cloud-connector.md#Example) Il record DNS deve essere risolto solo per i client di rete interni. non deve essere risolto per i client di rete esterni.
  
Dopo aver configurato DNS, connettersi a Skype for Business online usando Remote PowerShell con le credenziali di amministratore di Skype for Business. Per ulteriori informazioni, vedere [Configurare il computer per Windows PowerShell.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
Nella sessione di PowerShell, immettere i comandi seguenti per abilitare il bypass multimediale:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

L'abilitazione del bypass multimediale è un processo in due passaggi. Il cmdlet New-CsNetworkMedia non salva immediatamente la nuova configurazione. crea solo le impostazioni in memoria. L'oggetto creato da questo cmdlet deve essere salvato in una variabile e quindi assegnato alla proprietà MediaBypassSettings della configurazione di rete. Per ulteriori informazioni, vedere [Example: media bypass web site DNS records in complex multi-site environments.](deploy-media-bypass-in-cloud-connector.md#Example)
  
La replica tra i componenti locali e online può richiedere fino a 24 ore, pertanto Microsoft consiglia di eseguire i comandi necessari prima di abilitare gli utenti.
  
## <a name="confirm-media-bypass-settings"></a>Verificare le impostazioni di bypass multimediale

Puoi controllare le impostazioni di bypass multimediale come indicato di seguito. 
  
Per controllare la replica online nel pool tenant, eseguire il comando seguente in PowerShell remoto:
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Per controllare la replica locale, connettersi ai Mediation Server cloud Connector, eseguire il comando seguente in PowerShell e verificare che Enabled=True e AlwaysBypass=True
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

Per controllare le impostazioni del client, disconnettersi dal client Skype for Business, accedere di nuovo e verificare che il client abbia ricevuto l'URL del servizio nel modo seguente:
  
1. Aprire %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 
    
2. Cercare hybridconfigserviceinternalurl e verificare che l'URL corrisponda a quello definito.
    
## <a name="change-media-bypass-parameters"></a>Modificare i parametri di bypass multimediale

Gli amministratori tenant possono modificare il nome DNS del servizio Web eseguendo il cmdlet seguente:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> I client devono disconnettersi e accedere per ottenere il nuovo nome del servizio e riconoscere la modifica. 
  
## <a name="temporarily-disable-media-bypass"></a>Disabilitare temporaneamente il bypass multimediale

Questo scenario può essere utile per la risoluzione dei problemi o la manutenzione. Per disabilitare il servizio, eseguire i cmdlet seguenti:
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Dopo aver apportato la modifica, la replica delle modifiche in tutti i connettori cloud potrebbe richiedere del tempo. Per controllare lo stato della replica, eseguire il cmdlet seguente in PowerShell nei Mediation Server cloud Connector: 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

Dopo la replica delle modifiche, il servizio Web nel Mediation Server inizierà a rifiutare le richieste client per il servizio di bypass multimediale.
  
## <a name="disable-media-bypass-permanently"></a>Disabilitare in modo permanente il bypass multimediale

Per disabilitare definitivamente il bypass multimediale, un amministratore tenant deve eseguire i comandi seguenti: 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Un amministratore dovrà anche rimuovere gli indirizzi Web per il bypass multimediale dai server DNS interni. Dopo aver apportato la modifica, potrebbe essere necessario del tempo prima che le modifiche vengano replicate in tutte le appliance del connettore cloud. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Esempio: record DNS del sito Web bypass multimediale in ambienti multisolutore complessi
<a name="Example"> </a>

I client riceveranno l'indirizzo Web del servizio Web di bypass multimediale da un server DNS interno. Il nome del servizio Web sarà lo stesso per tutti i dispositivi Cloud Connector e i siti PSTN di Cloud Connector. In un ambiente multisito complesso, è consigliabile usare i criteri DNS di Windows 2016 per la gestione del traffico basato su Geo-Location, in modo che i client possano essere reindirizzati al servizio Web locale per la propria rete. 
  
Per ulteriori informazioni sui criteri DNS di Windows 2016, vedere Use [DNS Policy for Geo-Location Based Traffic Management with Primary Servers.](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location)
  
Di seguito è riportato un esempio di configurazione per una società con diversi siti che usano i criteri DNS di Windows 2016 per la Geo-Location del traffico basato su windows.
  
Il nome del servizio di bypass è "hybridvoice.adatum.biz".
  
Il sito di Amsterdam dispone di quattro appliance Cloud Connector distribuite con i seguenti indirizzi IP di Mediation Server:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
Il sito di Seattle dispone di tre appliance Cloud Connector distribuite con i seguenti indirizzi IP di Mediation Server:
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
Utilizzando Geo-Location traffico basato su server DNS, i server DNS verrebbero configurati nel modo seguente:
  
1. Creare subnet client DNS per entrambe le subnet di Amsterdam e Seattle.
    
2. Creare ambiti di zona DNS per adatum.biz sia per Amsterdam che per Seattle.
    
3. Creare record DNS in ogni ambito di zona DNS.
    
    Amsterdam
    
   - Tipo A;
    
   - Nome : hybridvoice nella adatum.biz DNS
    
   - Destinazione: 192.168.1.45
    
     Creare record aggiuntivi per mediation server aggiuntivi
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Seattle
    
   - Tipo A
    
   - Name : hybridvoice in adatum.biz DNS zone
    
   - Destinazione: 10.10.1.8
    
     Creare record aggiuntivi per mediation server aggiuntivi
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. Creare i criteri DNS che connettono le subnet client agli ambiti di zona appropriati per garantire la risoluzione DNS desiderata.
    
A questo punto, i client che effettuano query DNS dalla subnet di Amsterdam per hybridvoice.adatum.biz restituiranno il valore 192.168.1.45, 192.168.1.46, 192.168.1.47 e 192.168.1.48, mentre i client che effettuano lo stesso modulo di query Seattle restituiranno 10.10.1.8, 10.10.1.9 e 10.10.1.10.

> [!NOTE]
> Se l'applicazione CCE non sembra ottenere le impostazioni aggiornate, verificare se l'applicazione è in grado di contattare il tenant tramite Remote PowerShell. È possibile utilizzare Remote PowerShell per controllare lo stato dell'applicazione con Get-CsHybridPSTNAppliance o utilizzare PowerShell nell'host CCE per controllare lo stato con Get-CcApplianceStatus.

  
## <a name="see-also"></a>Vedere anche
<a name="Example"> </a>

[Pianificare il bypass multimediale in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)
