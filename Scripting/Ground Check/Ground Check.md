# Ground Check

오브젝트가 땅에 닿았는지 체크하기 위해서 다음 기능을 사용했습니다.

## 사용된 기능
- Physics.BoxCast


### BoxCast vs RayCast

> RayCast는 매우 얇은 광선을 쏘는 것과도 같기 때문에, 
> 오브젝트의 바닥면에 맞춰 감지하기엔 한계가 있습니다.
> 또한 RayCast를 오브젝트의 밑면 중앙에 한번만 사용할 경우,
> 오브젝트가 바닥의 끝자락에 걸쳐있을 때 공중에 있다고 감지할 가능성이 높습니다.
> 또한 Cast 거리를 매우 짧게 할 경우 평평한 바닥이 아닌 곳에서도 의도치 않은 결과를 받을 수 있습니다.
> 하지만 BoxCast는 평탄한 바닥이 아니여도, 바닥 끝에 걸쳐 있어도 바닥을 감지할 수 있습니다.
> 따라서 BoxCast를 채용했습니다.




### 함수 선언
```cs
public static bool BoxCast(Vector3 center, Vector3 halfExtents, Vector3 direction, out RaycastHit hitInfo, 
Quaternion orientation = Quaternion.identity, float maxDistance = Mathf.Infinity, int layerMask = DefaultRaycastLayers, 
QueryTriggerInteraction queryTriggerInteraction = QueryTriggerInteraction.UseGlobal);
```
### 매개변수

 자료형 | 변수 이름 | 의미 |
:--- |---|---
 `Vector3` |`center` | Box의 중심점입니다. Raycast의 origin과도 같습니다.
 `Vector3 ` | `halfExtents` | Box의 Scale 절반값입니다.
 `Vector3 ` |`direction` | cast 방향입니다.  
 `RaycastHit` | `hitInfo`| 감지된 개체에 대한 정보가 반환됩니다.
 `Quaternion` |`orientation` | Box의 회전값입니다.
 `float`| `maxDistance` | 최대 감지 거리입니다.
 `int`|`layerMask` | layerMask 값입니다.
 `QueryTriggerInteraction`|`queryTriggerinteraction` | 트리거 콜라이더 감지 여부입니다.

### 주의사항
* halfExtents 
  * Box의 크기 절반값을 지정한다는 것을 기억하세요. BoxCollider의 Size 값을 생각하시면 됩니다.
  * BoxCollider의 Size 값을 참조할때, lossyScale 등을 사용하여 Scale 값을 월드 기준으로 하셔야 합니다.
* direction 
  * 월드 기준이라는 것을 명심하세요.
* layerMask
  * 자료형이 int인 점때문에 maxDistance값 대신 들어갈 수 있습니다. 또한 오류가 검출되지 않습니다.


