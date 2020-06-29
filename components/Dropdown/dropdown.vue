<script>
    import Lang from 'src/mixin/lang.js';

    export default {
        name: 'Dropdown',
        mixins: [Lang],
        props: {
        },
        data() {
            return {
                isShow: false,
                button: '',
                menu: ''
            };
        },
        mounted() {

        },

        methods: {
            handleMouseenter() {
                this.isShow = true;
            },
            show() {
                console.log('123');
            },
            hide() {
                console.log('1231');
            }
        },
        render(h) {
            let Button, Menu;
            this.$slots.default.map((item, index) => {
                if (!item.tag) return;
                if (item.tag.indexOf('Menu') > -1) {
                    Menu = item;
                } else {
                    Button = item;
                }
            });

            return (
                <div >
                    { Button }
                    { Menu }
                </div>
            );
        }
    };

</script>
