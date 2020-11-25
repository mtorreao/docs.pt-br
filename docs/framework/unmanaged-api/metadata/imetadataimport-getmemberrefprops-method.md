---
title: Método IMetaDataImport::GetMemberRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
ms.openlocfilehash: 3237b67f8f711e9ef213d6fc66f1513c534fbdeb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733198"
---
# <a name="imetadataimportgetmemberrefprops-method"></a>Método IMetaDataImport::GetMemberRefProps

Obtém os metadados associados ao membro referenciado pelo token especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,
   [out] mdToken           *ptk,
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pbSig
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `mr`  
 no O token de MemberRef para o qual retornar metadados associados.  
  
 `ptk`  
 fora Um TypeDef ou TypeRef ou um token TypeSpec que representa a classe que declara o membro ou um token ModuleRef que representa a classe do módulo que declara o membro ou um MethodDef que representa o membro.  
  
 `szMember`  
 fora Um buffer de cadeia de caracteres para o nome do membro.  
  
 `cchMember`  
 no O tamanho solicitado em caracteres largos de `szMember` .  
  
 `pchMember`  
 fora O tamanho retornado em caracteres largos de `szMember` .  
  
 `ppvSibBlob`  
 fora Um ponteiro para a assinatura de metadados binários do membro.  
  
 `pbSig`  
 fora O tamanho em bytes de `ppvSigBlob` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor. h  
  
 **Biblioteca:** Incluído como um recurso no MsCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IMetaDataImport](imetadataimport-interface.md)
- [Interface IMetaDataImport2](imetadataimport2-interface.md)
