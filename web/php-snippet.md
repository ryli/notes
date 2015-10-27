# PHP Snippet

1. 过滤带表情的字符

    ```php
    function smarty_modifier_emojistrip($string){
        return preg_replace('/\xEE[\x80-\xBF][\x80-\xBF]|\xEF[\x81-\x83][\x80-\xBF]/', '', $string);
    }
    ```
