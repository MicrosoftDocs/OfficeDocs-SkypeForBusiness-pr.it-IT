---
title: Configurare l'integrazione tra Skype for Business Server locale e Outlook Web App
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Sintesi: integrazione di Skype for Business Server e Outlook Web App.'
ms.openlocfilehash: ee5676c0dbe88568af78a1c278eea8a46457cb5c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221186"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Configurare l'integrazione tra Skype for Business Server locale e Outlook Web App

**Riepilogo:** Integrazione di Skype for Business Server e Outlook Web App.

I clienti che utilizzano le distribuzioni di Skype for Business Server in locale possono configurare l'interoperabilità con Microsoft Outlook Web App in Microsoft Exchange online in una modalità di distribuzione ibrida. Le caratteristiche di interoperabilità includono accesso Single Sign-on e messaggistica immediata (IM) e integrazione della presenza con l'interfaccia di Outlook Web App. Per abilitare questa integrazione, è necessario configurare il server perimetrale nella distribuzione di Skype for Business Server locale completando le attività seguenti:

- Configurare uno spazio di indirizzi SIP condiviso

- Configurare un provider di hosting nel server perimetrale

- Verificare la replica dell'archivio di gestione centrale aggiornato

## <a name="configure-a-shared-sip-address-space"></a>Configurare uno spazio di indirizzi SIP condiviso

Per integrare Skype for Business Server locale con Exchange Online, è necessario configurare uno spazio di indirizzi SIP condiviso. Lo stesso spazio di indirizzi SIP del dominio è supportato sia da Skype for Business Server che dal servizio Exchange Online.

Se si utilizza Skype for Business Server Management Shell, configurare il server perimetrale per la federazione eseguendo il cmdlet **Set-CsAccessEdgeConfiguration** , utilizzando i parametri visualizzati nell'esempio seguente:

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- Il parametro **AllowFederatedUsers** consente di specificare se gli utenti interni sono autorizzati a comunicare con utenti provenienti da domini federati. Questa proprietà determina inoltre se gli utenti interni possono comunicare con gli utenti in uno scenario di spazio degli indirizzi SIP condiviso con Skype for Business Server ed Exchange Online.

Per informazioni dettagliate sull'uso di Skype for Business Server Management Shell, vedere [Skype for Business Server Management Shell](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurare un provider di hosting nel server perimetrale

Se si utilizza Skype for Business Server Management Shell, configurare un provider di hosting nel server perimetrale eseguendo il cmdlet **New-CsHostingProvider** , utilizzando i parametri nell'esempio seguente:

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Se si utilizza Microsoft 365 o Office 365 gestito da 21Vianet in Cina, sostituire il valore per il parametro ProxyFqdn in questo esempio ("exap.um.outlook.com") con il nome di dominio completo per il servizio gestito da 21Vianet: "exap.um.partner.outlook.cn". Se si utilizza Microsoft 365 o Office 365 GCC High, sostituire il valore per il parametro ProxyFqdn in questo esempio ("exap.um.outlook.com") con il nome di dominio completo per GCC High: "exap.um.office365.us".

- **Identity** specifica un identificatore di valore stringa univoco per il provider di hosting da creare (ad esempio, "Exchange Online"). I valori che contengono spazi devono essere racchiusi tra virgolette doppie.

- **Enabled** indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata. Questa impostazione deve essere impostata su true.

- **EnabledSharedAddressSpace** consente di indicare se il provider di hosting verrà utilizzato in uno scenario con spazio di indirizzamento SIP condiviso. Questa impostazione deve essere impostata su true.

- **HostsOCSUsers** indica se il provider di hosting viene utilizzato per ospitare Office Communications Server o Skype for Business Server. Questo valore deve essere impostato su false.

- **ProxyFQDN** specifica il nome di dominio completo (FQDN) del server proxy utilizzato dal provider di hosting. Per Exchange Online, il nome di dominio completo è exap.um.outlook.com.

- La **lingua locale** indica se il server proxy utilizzato dal provider di hosting è contenuto nella topologia di Skype for Business Server. Questo valore deve essere impostato su false.

- **VerificationLevel** Indica il livello di verifica consentito per i messaggi inviati e ricevuti dal provider ospitato. Specificare **UseSourceVerification**, che si basa sul livello di verifica incluso nei messaggi inviati dal provider di hosting. Se questo livello non viene specificato, il messaggio verrà rifiutato come non verificabile.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Verificare la replica dell'archivio di gestione centrale aggiornato

Le modifiche apportate utilizzando i cmdlet nelle sezioni precedenti vengono applicate automaticamente al server perimetrale e generalmente richiedono meno di un minuto per la replica. È possibile convalidare lo stato di replica e quindi verificare che le modifiche siano state applicate al server perimetrale utilizzando i cmdlet seguenti.

Per verificare gli aggiornamenti della replica, in un server interno della distribuzione di Skype for Business Server, eseguire il cmdlet seguente:

```powershell
Get-CsManagementStoreReplicationStatus
```
Controllare se il valore di UpToDate viene visualizzato come TRUE per tutte le repliche.

Per verificare che le modifiche siano state applicate, nel server perimetrale eseguire il cmdlet seguente:

```powershell
Get-CsHostingProvider -LocalStore
```
Controllare se le informazioni visualizzate corrispondono alle modifiche commesse nei passaggi precedenti.

## <a name="see-also"></a>Vedere anche

[Fornire agli utenti di Skype for Business Server la posta vocale sulla messaggistica unificata di Exchange ospitata](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Integrazione della messaggistica unificata di Exchange ospitata in Skype for Business Server](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
