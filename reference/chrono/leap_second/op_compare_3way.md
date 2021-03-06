# operator<=>
* chrono[meta header]
* std::chrono[meta namespace]
* function[meta id-type]
* cpp20[meta cpp]

```cpp
namespace std::chrono {
  constexpr strong_ordering
    operator<=>(const leap_second& x, const leap_second& y) noexcept;        // (1) C++20

  template <three_way_comparable_with<sys_seconds> Duration>
  constexpr auto
    operator<=>(const leap_second& x, const sys_time<Duration>& y) noexcept; // (2) C++20
}
```
* three_way_comparable_with[link /reference/compare/three_way_comparable.md]
* sys_seconds[link /reference/chrono/sys_time.md]
* sys_time[link /reference/chrono/sys_time.md]

## 概要
三方比較を行う。

- (1) : `leap_second`オブジェクト同士の三方比較を行う
- (2) : `leap_second`オブジェクトと[`sys_time`](/reference/chrono/sys_time.md)オブジェクトの三方比較を行う


## 戻り値
- (1) :
    ```cpp
    return x.date() <=> y.date();
    ```
    * date()[link date.md]

- (2) :
    ```cpp
    return x.date() <=> y;
    ```
    * x.date()[link date.md]


## 例外
投げない


## 備考
- この演算子により、`operator<`、`operator<=`、`operator>`、`operator>=`が使用可能になる


## バージョン
### 言語
- C++20

### 処理系
- [Clang](/implementation.md#clang): (9.0時点で実装なし)
- [GCC](/implementation.md#gcc): (9.2時点で実装なし)
- [Visual C++](/implementation.md#visual_cpp): (2019 Update 3時点で実装なし)
