---
title: Configurare l'integrazione tra Skype for Business Server e Outlook Web App locale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Riepilogo: integrare Skype for Business Server e Outlook Web App.'
ms.openlocfilehash: d207e366638b8b6fe163d68b527c9b6d33d7a418
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188129"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Configurare l'integrazione tra Skype for Business Server e Outlook Web App locale

**Riepilogo:** Integrare Skype for Business Server e Outlook Web App.

I clienti che usano distribuzioni locali Skype for Business Server possono configurare l'interoperabilità con Microsoft Outlook Web App in Microsoft Exchange online in modalità di distribuzione ibrida. Le caratteristiche di interoperabilità includono il Single Sign-on e la messaggistica istantanea (IM) e l'integrazione della presenza con l'interfaccia di Outlook Web App. Per abilitare questa integrazione, è necessario configurare l'Edge Server nella distribuzione di Skype for Business Server locale completando le attività seguenti:

- Configurare uno spazio di indirizzi SIP condiviso

- Configurare un provider di hosting nell'Edge Server

- Verificare la replica dell'archivio di gestione centralizzato aggiornato

## <a name="configure-a-shared-sip-address-space"></a>Configurare uno spazio di indirizzi SIP condiviso

Per integrare Skype for Business Server locale con Exchange Online, è necessario configurare uno spazio di indirizzi SIP condiviso. Lo stesso spazio per l'indirizzo del dominio SIP è supportato sia da Skype for Business Server che dal servizio Exchange Online.

Usando Skype for Business Server Management Shell, configura il server perimetrale per la federazione eseguendo il cmdlet **Set-CsAccessEdgeConfiguration** , usando i parametri visualizzati nell'esempio seguente:

```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- Il parametro **AllowFederatedUsers** specifica se gli utenti interni possono comunicare con utenti provenienti da domini federati. Questa proprietà determina anche se gli utenti interni possono comunicare con gli utenti in uno scenario di spazio di indirizzi SIP condiviso con Skype for Business Server ed Exchange Online.

Per informazioni dettagliate sull'uso di Skype for Business Server Management Shell, vedere [Skype for Business Server Management Shell](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurare un provider di hosting nell'Edge Server

Usando Skype for Business Server Management Shell, configura un provider di hosting nell'Edge Server eseguendo il cmdlet **New-CsHostingProvider** , usando i parametri nell'esempio seguente:

```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Se si usa Office 365 gestito da 21Vianet in Cina, sostituire il valore per il parametro ProxyFqdn in questo esempio ("exap.um.outlook.com") con il nome di dominio completo per il servizio gestito da 21Vianet: "exap.um.partner.outlook.cn". Se si usa Office 365 GCC High, sostituire il valore per il parametro ProxyFqdn in questo esempio ("exap.um.outlook.com") con il nome di dominio completo per GCC High: "exap.um.office365.us".

- **Identity** specifica un identificatore di valore di stringa univoco per il provider di hosting da creare, ad esempio "Exchange Online". I valori che contengono spazi devono essere racchiusi tra virgolette doppie.

- **Enabled ** indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata. Deve essere impostato su true.

- **EnabledSharedAddressSpace** indica se il provider di hosting verrà usato in uno scenario di spazio di indirizzi SIP condiviso. Deve essere impostato su true.

- **HostsOCSUsers** indica se il provider di hosting viene usato per ospitare Office Communications Server o Skype for Business Server. Deve essere impostato su false.

- **ProxyFqdn** specifica il nome di dominio completo (FQDN) per il server proxy usato dal provider di hosting. Per Exchange Online, il nome di dominio completo è exap.um.outlook.com.

- La **lingua locale** indica se il server proxy usato dal provider di hosting è contenuto nella topologia di Skype for Business Server. Deve essere impostato su false.

- **VerificationLevel** Indica il livello di verifica consentito per i messaggi inviati da e verso il provider ospitato. Specificare **UseSourceVerification**, che si basa sul livello di verifica incluso nei messaggi inviati dal provider di hosting. Se questo livello non è specificato, il messaggio verrà rifiutato come non verificabile.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Verificare la replica dell'archivio di gestione centralizzato aggiornato

Le modifiche apportate tramite i cmdlet nelle sezioni precedenti vengono applicate automaticamente all'Edge Server e in genere richiedono meno di un minuto per la replica. È possibile convalidare lo stato della replica e verificare che le modifiche siano state applicate all'Edge Server usando i cmdlet seguenti.

Per verificare gli aggiornamenti della replica, in un server interno della distribuzione di Skype for Business Server, eseguire il cmdlet seguente:

```
Get-CsManagementStoreReplicationStatus
```
Controlla se il valore di UpToDate viene visualizzato TRUE per tutte le repliche.

Per verificare che le modifiche siano state applicate, nel server perimetrale eseguire il cmdlet seguente:

```
Get-CsHostingProvider -LocalStore
```
Verificare che le informazioni visualizzate corrispondano alle modifiche apportate nei passaggi precedenti.

## <a name="see-also"></a>Vedere anche

[Fornire agli utenti di Skype for Business Server Voice mail nella messaggistica unificata di Exchange ospitata](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Integrazione della messaggistica unificata di Exchange ospitata in Skype for Business Server](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
