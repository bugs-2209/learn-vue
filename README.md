## TỔNG HỢP KIẾN THỨC CƠ BẢN

1. <span style="font-weight: bold">createApp</span> và <span style="font-weight: bold">mount</span> là 2 phương thức quan trọng được sử dụng để khởi tạo và kết nối ứng dụng Vue với một phần tử trên trang web
 - createApp(options)
   - <span>Trong createApp luôn luôn có options, options là 1 đối tượng để chứa các cấu hình cho ứng dụng Vue. Các cấu hình này gồm: data, methods, computed, ...</span>

 - mount(rootElementId)
   - <span>Dùng để binding ra root container</span>

Ví dụ:
```vue
    createApp({
        data () {
            fullName: BugCreator
        },
        methods () {
            handleChangeName() {
                //TODO
            }
        }, 
        computed () {
            // TODO
        }
    }).mount("#app");
```

2. Template: Là 1 phần của một component chứa các mã HTML mà vue sẽ rendering ra màn hình.

3. Event: Các event trong Vue giống với Javascript (click, change, input, mouseover, ...). Có 2 cách để sử dụng event:
   - Full: v-on:{event}="onEventName"
   - Shorthand: @click="onEventName"
   - Refer document: [Events](https://vuejs.org/guide/components/events.html)

4. Condition Rendering:
   - v-if: Khi sử dụng v-if lên template, element sẽ không được hiển thị cho đến khi giá trị v-if="true"
   - v-show: Khi sử dụng v-show. Sẽ render toàn bộ element nhưng hiển thị dưới dạng style là display: none
   - Refer document: Refer Document: [Conditional Rendering](https://vuejs.org/guide/essentials/conditional.html)

    Ví dụ v-if
    ```vue
        <div v-if="true">
          Display element when v-if is true
        </div>
    ```
    
    Ví dụ v-show
    ```vue
        <div v-show="true" style="display: block">
          Update style display none when v-show is false
        </div>
    ```

5. Render list: Dùng v-for để có thể render 1 list danh sách khi data trả về dạng mảng
    - Refer document: [List Rendering](https://vuejs.org/guide/essentials/list.html)

    Ví dụ:
    ```vue
        <div class="card">
            <div class="card-content" v-for="product in products">
                //TODO
            </div>
        </div>
    ```
   
6. Binding dữ liệu vào các thuộc tính(attribute): Để binding thêm dữ liệu vào attribute mong muốn, cần sử dụng `v-bind:{attribute}` hoặc sử dụng shorthand `:{attribute}`
   - Refer document: [Class and Style Bindings](https://vuejs.org/guide/essentials/class-and-style.html)
   
    Ví dụ:
    ```vue
        const isActive = ref(true)
        const hasError = ref(false)
    
        <div class="static" :class="{ active: isActive, 'text-danger': hasError }">
        </div>
        
        It will render
   
        <div class="static active"></div>
    ```

7. Computed: Mục đích để xử lý dữ liệu cần thiết trước khi render ra màn hình.
    - Các bài toán thường gặp cần sử dụng đến computed:
      - Dùng để tính toán bill trước khi hiển thị ra ngoài
      - Lọc các sản phẩm theo conditional
      - ...
   - Document Refer: [Computed Properties](https://vuejs.org/guide/essentials/computed.html)
    
