---
title: Configurare l'integrazione tra Skype for Business Server locale e Outlook Web App
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Riepilogo: integrare Skype for Business Server e Outlook Web App.'
ms.openlocfilehash: 0a6358c93356bd059aeed34033b07916d856bf10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833966"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Configurare l'integrazione tra Skype for Business Server locale e Outlook Web App

**Riepilogo:** Integrare Skype for Business Server e Outlook Web App.

I clienti che utilizzano distribuzioni locali di Skype for Business Server possono configurare l'interoperabilità con Microsoft Outlook Web App in Microsoft Exchange Online in modalità di distribuzione ibrida. Le funzionalità di interoperabilità includono l'accesso Single #A0 e la messaggistica istantanea e l'integrazione della presenza con l'interfaccia di Outlook Web App. Per abilitare questa integrazione, è necessario configurare il server perimetrale nella distribuzione di Skype for Business Server locale completando le attività seguenti:

- Configurare uno spazio di indirizzi SIP condiviso

- Configurare un provider di hosting nel server perimetrale

- Verificare la replica dell'archivio di gestione centrale aggiornato

## <a name="configure-a-shared-sip-address-space"></a>Configurare uno spazio di indirizzi SIP condiviso

Per integrare Skype for Business Server locale con Exchange Online, è necessario configurare uno spazio di indirizzi SIP condiviso. Lo stesso spazio di indirizzi del dominio SIP è supportato sia da Skype for Business Server che dal servizio Exchange Online.

Utilizzando Skype for Business Server Management Shell, configurare il server perimetrale per la federazione eseguendo il cmdlet **Set-CSAccessEdgeConfiguration,** utilizzando i parametri visualizzati nell'esempio seguente:

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **Il parametro AllowFederatedUsers** consente di specificare se agli utenti interni è consentito comunicare con utenti di domini federati. Questa proprietà determina inoltre se gli utenti interni possono comunicare con gli utenti in uno scenario di spazio di indirizzi SIP condiviso con Skype for Business Server ed Exchange Online.

Per informazioni dettagliate sull'utilizzo di Skype for Business Server Management Shell, vedere [Skype for Business Server Management Shell.](../../manage/management-shell.md)

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurare un provider di hosting nel server perimetrale

Utilizzando Skype for Business Server Management Shell, configurare un provider di hosting nel server perimetrale eseguendo il cmdlet **New-CsHostingProvider,** utilizzando i parametri nell'esempio seguente:

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Se si utilizza Microsoft 365 o Office 365 gestito da 21Vianet in Cina, sostituire il valore per il parametro ProxyFqdn in questo esempio ("exap.um.outlook.com") con il nome di dominio completo per il servizio gestito da 21Vianet: "exap.um.partner.outlook.cn". Se si utilizza Microsoft 365 o Office 365 GCC High, sostituire il valore per il parametro ProxyFqdn in questo esempio ("exap.um.outlook.com") con il nome di dominio completo per GCC High: "exap.um.office365.us".

- **Identity** specifica un identificatore di valore stringa univoco per il provider di hosting che si sta creando (ad esempio, "Exchange Online"). I valori che contengono spazi devono essere racchiusi tra virgolette doppie.

- **Enabled** indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata. Deve essere impostata su True.

- **EnabledSharedAddressSpace** consente di indicare se il provider di hosting verrà utilizzato in uno scenario con spazio di indirizzamento SIP condiviso. Deve essere impostata su True.

- **HostsOCSUsers** indica se il provider di hosting viene utilizzato per ospitare Office Communications Server o Skype for Business Server. Deve essere impostata su False.

- **ProxyFQDN** specifica il nome di dominio completo (FQDN) del server proxy utilizzato dal provider di hosting. Per Exchange Online, il nome di dominio completo è exap.um.outlook.com.

- **IsLocal** indica se il server proxy utilizzato dal provider di hosting è contenuto nella topologia di Skype for Business Server. Deve essere impostata su False.

- **VerificationLevel** Indica il livello di verifica consentito per i messaggi inviati da e verso il provider ospitato. Specificare **UseSourceVerification**, che si basa sul livello di verifica incluso nei messaggi inviati dal provider di hosting. Se questo livello non viene specificato, il messaggio verrà rifiutato come non verificabile.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Verificare la replica dell'archivio di gestione centrale aggiornato

Le modifiche apportate utilizzando i cmdlet nelle sezioni precedenti vengono applicate automaticamente al server perimetrale e in genere la replica richiede meno di un minuto. È possibile convalidare lo stato della replica e quindi verificare che le modifiche sono state applicate al server perimetrale utilizzando i cmdlet seguenti.

Per verificare gli aggiornamenti della replica, in un server interno nella distribuzione di Skype for Business Server, eseguire il cmdlet seguente:

```powershell
Get-CsManagementStoreReplicationStatus
```
Verificare se il valore UpToDate mostra VERO per tutte le repliche.

Per verificare che le modifiche sono state applicate, nel server perimetrale eseguire il cmdlet seguente:

```powershell
Get-CsHostingProvider -LocalStore
```
Verificare se le informazioni visualizzate corrispondono alle modifiche apportate nei passaggi precedenti.

## <a name="see-also"></a>Vedere anche

[Fornire la segreteria telefonica degli utenti di Skype for Business Server nella messaggistica unificata di Exchange ospitata](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Integrazione della messaggistica unificata di Exchange ospitata in Skype for Business Server](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
