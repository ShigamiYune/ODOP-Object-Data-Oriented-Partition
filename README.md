# ODOP : Object-Data Oriented Partition

Đề xuất mô hình kết hợp mới cho hệ thống compoent 

## Tổng quan:
ODOP là 1 mô hình kết hợp giữa DOD và ECS đồng thời giữ tính mạch lạc và dễ viết script như OOP

## Giới thệu

- ComponentStorage<T> : là class lưu trữ data của component
- ComponentLifeCycle : là class giúp gọi đến toàn bộ hàm vòng đời (life cycle) của ComponentStorage<T>
- Index : là struct chứa thông tin vị trí của 1 component trong ComponentStorage
- IndexHandle : là class ...
- CompPtr<T> : là class cung cấp cách lấy data và định nghĩa cách xử lý các sự sự kiện như OnColliderEnter, OnEnable ...
- CompHook<T> : là class cho phép dev tuỳ chỉnh hàm ảo OnEvent
- Comp<T> : là 1 class bọc, cung cấp sự ngắn ngọn khi viết code
- CompOOP<T> : cũng là 1 class bọc nhưng sẽ cung cấp đầy đủ tính năng OOP cho component hơn
- Component : là class cần kế thừa chính
- CompoenentOOP : là lớp kế thừa từ Component và cung cấp thêm virtual

## Cách viết cơ bản 

``` c++

class IsRun : public Component {
public:
  inline void Update(float dt) {
    std::cout << "run" << std::endl;
  }
};
```
