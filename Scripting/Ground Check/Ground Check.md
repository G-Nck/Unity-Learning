# Ground Check

오브젝트가 땅에 닿았는지 체크하기 위해서 다음 기능을 사용했습니다.

## 사용된 기능
- BoxCast
- LayerMask
- Collider


### BoxCast vs RayCast

> RayCast는 매우 얇은 광선을 쏘는 것과도 같기 때문에, 
> 오브젝트의 바닥면에 맞춰 감지하기엔 한계가 있습니다.
> 또한 RayCast를 오브젝트의 밑면 중앙에 한번만 사용할 경우,
> 오브젝트가 바닥의 끝자락에 걸쳐있을 때 공중에 있다고 감지할 가능성이 높습니다.
> 또한 Cast 거리를 매우 짧게 할 경우 평평한 바닥이 아닌 곳에서도 의도치 않은 결과를 받을 수 있습니다.
> 하지만 BoxCast는 평탄한 바닥이 아니여도, 바닥 끝에 걸쳐 있어도 바닥을 감지할 수 있습니다.
> 따라서 BoxCast를 채용했습니다.


### LayerMask
> Ground Check라 하면 엄연히 '땅' 만을 감지해야 한다는 뜻입니다.
> 따라서 BoxCast가 땅만을 감지하기 위해 LayerMask를 사용합니다.

### Collider
> 단순히 BoxCast 함수에서 Collider의 밑면 Scale을 받아오기 위해 사용합니다.


