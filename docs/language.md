# Language Definition

    document = [ title ], [ { lines } ], <EOF>;
    title = token_string, { white_space, token_string }, <EOL>;
    lines = blank_line | header_line | tasks_line | text_line, <EOL>;
    
    blank_line = [ white_space ];
    header_line = token_string, { white_space, token_string }, ":";
    tasks_line = [ white_space ], blocked | cancelled | completed | event | future | handed_off | migrated | question | reassigned | response | task;
    text_line = [ white_space ], token_string;

    task = [ "!" ], "*", task_text;
    blocked = [ "!" ], "*|", assigned_text;
    question = [ "!" ], "?", task_text | assigned_text;
    event = [ "!" ], "o", event_text;
    note = [ "!" ], "-", task_text;
    completed = [ "!" ], "x", task_text | event_text | assigned_text;
    future = [ "!" ], "<", task_text | assigned_text, "(", date_string, "),"[", [ path ], filename, "]";
    migrated = [ "!" ], ">", task_text | assigned_text, "("[", [ path ], filename, "]";
    cancelled = "---", task_text | event_text | assigned_text;
    handed_off = "=>", assigned_text;
    response = "<=", assigned_text;

    task_text = white_space, token_string;
    event_text = white_space, token_string, [ time_string ];
    assigned_text = task_text, "(", person_list, ")";

    person_list = person_tag, { ",", white_space, person_tag };
    
    filename = token, { ( "-" | "_" | "." ), token}, ".", frozentasks_extension;
    path = ? canonical system path ?;
    frozentasks_extension = "tasks";

    token_string = token, { white_space, token };
    token = string | data_string | tag | time_string;
    person_tag = tag | "@{",string, { white_space, string }, "}";
    tag = "@", string;

    date_string = ? valid date string ?;
    string = character | digit | symbol, { character | digit | symbol };
    time_string = ? system time string ?;

    (* Currently defined against a US standard keyboard *)
    character = "a" | "b" | "c" | "d" | "e" | "f" | "g"| "h" | "i" | "j" | "k" | "l" | "m" | "n" | "o" | "p" | "q" | "r" | "s" | "t" | "u" | "v" | "w" | "x" | "y" | "z" | "A" | "B" | "C" | "D" | "E" | "F" | "G" | "H" | "I" | "J" | "K" | "L" | "M" | "N" | "O" | "P" | "Q" | "R" | "S" | "T" | "U" | "V" | "W" | "X" | "Y" | "Z";
    digit = "0" | "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9";
    symbol = "*" | "^" | "~" | "@" | "#" | "$" | "%" | "^" | "&" | "(" | ")" | "_" | "-" | "[" | "]" | "{" | "}" | "|" | "\" | ";" || "<" | ">" | "/" | punctuation;
    punctuation = "`" | "!" | "." | "'" | '"' | ":" | "?" | ",";
    white_space = ? white_space characters ?; (* includes tab characters *)
