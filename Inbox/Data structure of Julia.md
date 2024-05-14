---
icon: TiHelp
---
#Tutorial/Program 

# Tuple
initial time: about $0.04$ ns
allocations: $0$ bytes
getindex time: about $0.04$ ns
```julia
# tuple
a = (1.0,2.0,3.0)
```
# NamedTuple
initial time: about $0.04$ ns
allocations: $0$ bytes
getindex time: about $0.04$ ns
```julia
# namedtuple
a = (a=1,b=2,c=3)
```
# Vector
initial time: about $30$ ns
allocations: $80+8\times n$ bytes
getindex time: about $1.6$ ns
```julia
# vector
a = [1,2,3]
```

# Dict
initial time: about $170$ ns
allocations: $688+8\times n$ bytes
getindex time: about $4.3$ ns
```julia
# dict
a = Dict([1=>1.0,2=>2.0,3=>3.0])
```
# Struct
initial time: about $0.04$ ns
allocations: $0$ bytes
getproperty time: $0.04$ bytes
```julia
# struct
struct T
	a::Int
	b::Float64
	c::Vector{Float64}
end
```
